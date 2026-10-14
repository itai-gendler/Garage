---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Forget Adapter in the scanner's adapter picker"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product disconnects and clears the saved adapter"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [OBD2 adapter] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Forget the adapter from the scanner

## Trigger

The adapter in the car is not the one saved.

## Outcome

The scanner is disconnected and asks for an adapter.
