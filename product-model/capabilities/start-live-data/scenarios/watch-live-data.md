---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Start Live Data"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product repeatedly reads the sensors the vehicle supports and shows them as they change"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Watch live data

## Trigger

The Owner wants to watch the engine while it runs.

## Outcome

Live readings update on screen; nothing is kept.
