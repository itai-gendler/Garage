---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Parts tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "Nothing has been recorded for the vehicle's parts and fluids"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [Oil, Ignition, Filters, Tires, Wipers] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product shows values estimated from the vehicle's year, make, model and decoded engine, with a reminder to verify them in the owner's manual"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model, Trim, Engine and drivetrain specs, Fuel type, Body specs] }
    contexts: { app: { place: garage-app::vehicle } }
---

# See estimated values

## Trigger

The Owner has not filled in the cheat sheet.

## Outcome

The Owner sees a starting point, marked as needing verification.

## Edge cases

- An electric vehicle shows N/A for oil, spark plug gap and the engine air filter.
