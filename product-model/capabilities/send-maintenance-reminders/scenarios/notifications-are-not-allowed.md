---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The check runs but Garage may not post notifications"
    kind: condition
    unattended: true
    entities: []
    contexts: { app: { place: garage-app } }
  - text: "The Product posts nothing"
    kind: product
    entities: []
    contexts: { app: { place: garage-app } }
---

# Notifications are not allowed

## Trigger

Notification permission was never granted or was withdrawn.

## Outcome

No notification appears; the schedule and widget still show what is due.
