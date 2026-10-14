---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Fuel tab of a plug-in hybrid"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The vehicle is electrified but not purely electric"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [Fuel type, Engine and drivetrain specs] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner switches between Charging and Fuel, each showing how many entries it holds"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# Switch between charging and fuel

## Trigger

The vehicle takes both fuel and electricity.

## Outcome

Both logs are available, and both kinds of entry can be added.
