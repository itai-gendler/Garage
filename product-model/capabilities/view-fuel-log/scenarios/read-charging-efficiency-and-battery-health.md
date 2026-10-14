---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Fuel tab of an electric vehicle"
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
  - text: "The Product lists charging sessions and shows efficiency in Wh/mi or kWh/100km and MPGe, total spent, and how the estimated full-charge range has changed since the first reading"
    kind: product
    actor: owner
    entities:
      - { entity: charging-session, effect: reads, facts: [Date, Odometer, Energy added, Charger speed, Battery start, Battery end, Total cost, Vendor, Vendor type, Range at full charge] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Read charging efficiency and battery health

## Trigger

The Owner drives an electric vehicle.

## Outcome

The Owner sees energy use and battery health; there is no fuel list.
