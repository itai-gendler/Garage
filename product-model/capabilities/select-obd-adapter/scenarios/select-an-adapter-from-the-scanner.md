---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Pair OBD2 Adapter or Change in the OBD2 Scanner and picks an adapter"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product saves the adapter and starts a scan with it"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [OBD2 adapter] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Select an adapter from the scanner

## Trigger

The Owner opens the scanner without a working adapter.

## Outcome

The adapter is saved and the scanner begins connecting to it.
