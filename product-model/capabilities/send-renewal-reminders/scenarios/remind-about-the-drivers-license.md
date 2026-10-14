---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The daily check comes round with the Owner's driver's license expiring within the notice window or expired"
    kind: condition
    unattended: true
    entities:
      - { entity: drivers-license, effect: reads, facts: [Expiration] }
      - { entity: settings, effect: reads, facts: [Document renewal reminders, Document expiration notice window] }
      - { entity: owner, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
  - text: "The Product posts a Driver's License Renewal notification"
    kind: product
    entities:
      - { entity: drivers-license, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
---

# Remind about the driver's license

## Trigger

The license nears expiry.

## Outcome

The Owner is reminded; tapping the notification opens the Driver's License tab.
