---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Edit vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner changes details or photos and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product saves the vehicle, removes photos taken off it, and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: changes, facts: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos] }
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product returns to My Vehicles"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
---

# Change a vehicle's details

## Trigger

Something about the vehicle was wrong or has changed.

## Outcome

The vehicle shows the new details everywhere.

## Edge cases

- Leaving without saving keeps the original photos.
