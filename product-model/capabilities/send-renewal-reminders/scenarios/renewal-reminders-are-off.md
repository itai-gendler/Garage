---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The check runs with document renewal reminders turned off"
    kind: condition
    unattended: true
    entities:
      - { entity: settings, effect: reads, facts: [Document renewal reminders] }
    contexts: { app: { place: garage-app } }
  - text: "The Product posts no renewal notifications and withdraws the driver's license reminder"
    kind: product
    entities:
      - { entity: drivers-license, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
---

# Renewal reminders are off

## Trigger

The Owner turned renewal reminders off.

## Outcome

No document or license notifications appear.
