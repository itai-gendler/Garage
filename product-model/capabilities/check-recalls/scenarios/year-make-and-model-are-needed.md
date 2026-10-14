---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Recalls tab of a vehicle missing its year, make or model"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product does not ask NHTSA and explains which details the vehicle needs"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Year, make and model are needed

## Trigger

The vehicle is incomplete.

## Outcome

No recalls are shown until the vehicle has a year, make and model.
