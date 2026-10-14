---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The garage holds vehicles to choose from"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner opens Default Vehicle and picks one, or First vehicle added (default)"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the choice and refreshes the home screen widgets"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Default vehicle] }
    contexts: { app: { place: garage-app::settings } }
---

# Choose the default vehicle

## Trigger

The Owner wants shortcuts and widgets to act on a particular vehicle.

## Outcome

Quick actions, tiles and widgets now open the chosen vehicle.
