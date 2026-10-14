---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Specs tab of a vehicle added without a decoded VIN"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product explains that decoding the VIN on the Edit screen fills in the specs"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# No specs yet

## Trigger

The vehicle was added by hand.

## Outcome

The Owner knows how to get the specs.
