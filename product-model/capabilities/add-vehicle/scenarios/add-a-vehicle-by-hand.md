---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Add vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Owner enters at least a make, with whatever else they know, and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product adds the vehicle without decoded specs"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: creates, facts: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos] }
    contexts: { app: { place: garage-app::vehicle-editor } }
---

# Add a vehicle by hand

## Trigger

The vehicle has no VIN to hand, or NHTSA does not know it.

## Outcome

The vehicle is in the garage; its Specs tab stays empty.
