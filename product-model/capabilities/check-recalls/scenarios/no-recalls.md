---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Recalls tab"
    kind: actor
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product finds no campaigns for the model and says so, crediting NHTSA"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
    contexts: { app: { place: garage-app::vehicle } }
---

# No recalls

## Trigger

The model has no recalls.

## Outcome

The Owner knows there is nothing open.
