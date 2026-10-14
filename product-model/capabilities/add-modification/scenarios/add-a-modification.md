---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Add on the Mods tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner enters a title, category, description, installation date, cost, product link and up to six photos, and taps Save Modification"
    kind: actor
    actor: owner
    entities:
      - { entity: modification, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the modification"
    kind: product
    actor: owner
    entities:
      - { entity: modification, effect: creates, facts: [Title, Category, Description, Installation date, Cost, Product link, Photos] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Add a modification

## Trigger

Something was fitted to the vehicle.

## Outcome

The modification is on the Mods tab.
