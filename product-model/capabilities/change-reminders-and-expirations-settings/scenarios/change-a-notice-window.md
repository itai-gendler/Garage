---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner picks how far ahead maintenance by mileage, maintenance by time or document expirations should be flagged"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the window"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Maintenance mileage notice window, Maintenance time notice window, Document expiration notice window] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product checks every vehicle's reminders again straight away"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::settings } }
---

# Change a notice window

## Trigger

The Owner wants earlier or later warning.

## Outcome

Upcoming statuses, notifications and widgets reflect the new window at once.
