---
kind: primary
routes:
  app: Garage app
steps:
  - text: "An adapter is saved"
    kind: condition
    entities:
      - { entity: settings, effect: reads, facts: [OBD2 adapter] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner taps Forget Adapter"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product clears the saved adapter"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [OBD2 adapter] }
    contexts: { app: { place: garage-app::settings } }
---

# Forget the adapter

## Trigger

The Owner no longer uses the adapter.

## Outcome

No adapter is saved; the scanner asks for one next time.
