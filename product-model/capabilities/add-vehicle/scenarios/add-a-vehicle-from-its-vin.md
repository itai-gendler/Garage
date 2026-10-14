---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Add vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Owner types the 17-character VIN"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product decodes the VIN with NHTSA and fills in year, make, model, trim, drivetrain and fuel type, keeping anything NHTSA leaves blank"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Owner adds photos, chooses New or Used, enters the initial mileage and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product adds the vehicle with the decoded specs and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: creates, facts: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos, Engine and drivetrain specs, Body specs, Weights and towing, Manufacturing] }
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product returns to My Vehicles"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
---

# Add a vehicle from its VIN

## Trigger

The Owner has a new vehicle to track.

## Outcome

The vehicle is in the garage with its decoded specs and appears on My Vehicles.

## Edge cases

- Decoding starts by itself once 17 characters are typed; Decode runs it again.
- NHTSA placeholder values such as Not Applicable are left out of the specs.
- Up to three photos can be added, each framed by dragging.
