---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner leaves the title empty"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "Save Modification stays unavailable"
    kind: condition
    entities:
      - { entity: modification, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# A title is required

## Trigger

The modification has no title.

## Outcome

Nothing is added.
