---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Stop Live Data"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product stops reading the sensors"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Stop watching live data

## Trigger

The Owner has seen enough.

## Outcome

The readings stop updating.
