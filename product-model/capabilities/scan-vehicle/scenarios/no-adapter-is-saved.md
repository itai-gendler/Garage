---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner opens the scanner with no adapter saved"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product explains how to plug in and pair an adapter and offers Pair OBD2 Adapter"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: reads, facts: [OBD2 adapter] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# No adapter is saved

## Trigger

The Owner has not set up an adapter.

## Outcome

No scan runs until an adapter is selected.
