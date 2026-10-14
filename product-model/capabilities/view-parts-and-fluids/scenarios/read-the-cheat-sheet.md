---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Parts tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product shows the recorded oil, ignition, filter, tire and wiper specifications"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Oil, Ignition, Filters, Tires, Wipers] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Read the cheat sheet

## Trigger

The Owner is buying parts or fluids.

## Outcome

The part numbers and sizes are at hand.
