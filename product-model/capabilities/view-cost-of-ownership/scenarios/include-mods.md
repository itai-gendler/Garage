---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner switches Include mods on"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product remembers the choice and adds modifications to the total and the breakdown"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Include mods in cost] }
      - { entity: modification, effect: reads, facts: [Installation date, Cost, Title, Category] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Include mods

## Trigger

The Owner counts upgrades as part of what the vehicle costs.

## Outcome

Mods are part of the total until the switch is turned off again.
