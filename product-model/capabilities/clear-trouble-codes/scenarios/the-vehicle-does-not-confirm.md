---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner confirms Clear Codes"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product asks the vehicle to clear its codes but gets no confirmation"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product asks the Owner to turn the engine off with the ignition on and try again"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# The vehicle does not confirm

## Trigger

The engine is running or the adapter times out.

## Outcome

Nothing is logged.
