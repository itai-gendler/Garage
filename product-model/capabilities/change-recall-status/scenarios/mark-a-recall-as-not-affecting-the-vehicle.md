---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner picks Does Not Affect Vehicle on an open recall"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product keeps the recall as not affecting this vehicle"
    kind: product
    actor: owner
    entities:
      - { entity: recall, effect: changes, from: Open, to: "Does not affect", facts: [] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Mark a recall as not affecting the vehicle

## Trigger

The campaign covers the model but not this vehicle.

## Outcome

The recall shows as Not Affected.
