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
  - text: "The Owner taps Scan VIN and points the camera at the VIN barcode"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product reads the VIN from the barcode and decodes it with NHTSA"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Owner checks the details and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product adds the vehicle with the decoded specs"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: creates, facts: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos, Engine and drivetrain specs, Body specs, Weights and towing, Manufacturing] }
    contexts: { app: { place: garage-app::vehicle-editor } }
---

# Scan the VIN barcode

## Trigger

The VIN is easier to scan than type.

## Outcome

The vehicle is added as if the VIN had been typed.
