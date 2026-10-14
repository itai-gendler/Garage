---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete on a fill-up and confirms"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product deletes it and works the economy out again"
    kind: product
    actor: owner
    entities:
      - { entity: fill-up, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete a fill-up

## Trigger

A fill-up should not be there.

## Outcome

The fill-up is gone from the log and from the economy figures.
