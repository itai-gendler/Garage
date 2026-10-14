---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens a modification, taps Edit, changes it and saves"
    kind: actor
    actor: owner
    entities:
      - { entity: modification, effect: reads, facts: [Title, Category, Description] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product saves the modification"
    kind: product
    actor: owner
    entities:
      - { entity: modification, effect: changes, facts: [Title, Category, Description, Installation date, Cost, Product link, Photos] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Change a modification

## Trigger

A modification's details changed.

## Outcome

The Mods tab shows the new details.
