---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Fuel tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product lists fill-ups newest first, marking partial ones and showing the economy each full tank completed"
    kind: product
    actor: owner
    entities:
      - { entity: fill-up, effect: reads, facts: [Date, Odometer, Volume, Total cost, Price per volume, Full tank] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product shows average, best and worst economy, total spent, and a trend chart with a rolling average and unusual tanks flagged"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# Read fuel economy

## Trigger

The Owner wants to know how the vehicle is doing on fuel.

## Outcome

Economy is shown in mpg or L/100km, following the chosen units.

## Edge cases

- Unusual tanks are flagged only once there are at least four economy readings.
