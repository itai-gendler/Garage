---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner leaves the category or description empty, or ticks Inspected only without both remind-in values"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "Save stays unavailable"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# A description and category are required

## Trigger

The form is incomplete.

## Outcome

No record is added until a category and description are given, and an inspection has both remind-in values.
