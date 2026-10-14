---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Schedule tab of a battery electric vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The vehicle's decoded fuel and electrification, or its make and model, mark it as purely electric"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [Fuel type, Engine and drivetrain specs, Make, Model, Trim] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product leaves out engine tasks such as oil changes, spark plugs and coolant flushes"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# A pure electric vehicle's schedule

## Trigger

The vehicle has no combustion engine.

## Outcome

Only tasks that apply to an electric vehicle are suggested.
