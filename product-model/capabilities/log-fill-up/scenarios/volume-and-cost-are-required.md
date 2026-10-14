---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner leaves the odometer empty, or enters a volume or total cost of zero"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "Save stays unavailable"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# Volume and cost are required

## Trigger

The fill-up is incomplete.

## Outcome

Nothing is recorded until odometer, volume and a total cost above zero are given.
