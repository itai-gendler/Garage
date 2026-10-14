---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Expenses tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The vehicle has no maintenance, fuel or charging entries in the period"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product invites the Owner to add maintenance or fuel entries"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# No costs yet

## Trigger

Nothing has been recorded.

## Outcome

The Owner is pointed to logging entries.
