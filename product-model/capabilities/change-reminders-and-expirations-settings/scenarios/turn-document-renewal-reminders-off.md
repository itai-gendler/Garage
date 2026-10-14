---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner switches Document Renewal Reminders off"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the switch and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Document renewal reminders] }
    contexts: { app: { place: garage-app::settings } }
---

# Turn document renewal reminders off

## Trigger

The Owner no longer wants document notifications.

## Outcome

Expiring registrations, inspections, insurance, permits and the driver's license are no longer notified; turning the switch on again resumes them.
