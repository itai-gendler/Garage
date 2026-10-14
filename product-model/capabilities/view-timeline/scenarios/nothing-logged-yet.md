---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Timeline tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The vehicle has no maintenance records"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
      - { entity: maintenance-record, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product invites the Owner to add the first record"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# Nothing logged yet

## Trigger

A new vehicle's timeline is opened.

## Outcome

The Owner is pointed to adding a record.
