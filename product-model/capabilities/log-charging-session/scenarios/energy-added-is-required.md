---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner leaves the odometer or total cost empty, or enters zero kWh"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "Save stays unavailable"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# Energy added is required

## Trigger

The session is incomplete.

## Outcome

Nothing is recorded until odometer, a total cost and kWh above zero are given.
