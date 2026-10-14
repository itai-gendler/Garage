---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Send Test Notification"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "Garage may post notifications"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product posts a test notification and confirms it was sent"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# Send a test notification

## Trigger

The Owner wants to check notifications work.

## Outcome

A Test Notification appears on the phone.
