---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner taps Send Test Notification"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "Notification permission has not been granted"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product posts nothing and explains that notifications are disabled for Garage"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# Notifications are blocked

## Trigger

The Owner tests notifications without permission.

## Outcome

Nothing is posted; the Owner is told to enable notifications to receive reminders.
