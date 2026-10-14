---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete Modification and confirms"
    kind: actor
    actor: owner
    entities:
      - { entity: modification, effect: reads, facts: [Title] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product deletes the modification and its photos"
    kind: product
    actor: owner
    entities:
      - { entity: modification, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete a modification

## Trigger

The modification was removed from the vehicle.

## Outcome

It is gone from the Mods tab and from cost of ownership.
