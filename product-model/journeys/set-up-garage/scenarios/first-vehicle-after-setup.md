---
kind: primary
result: achieved
routes:
  app: Garage app
steps:
  - text: "The Owner chooses units, language and currency and taps Get Started"
    kind: actor
    capability: get-started
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::setup } }
  - text: "The Product saves the choices, marks setup completed and opens My Vehicles"
    kind: product
    capability: get-started
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Units, Currency, Affiliate links, Setup completed] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::setup } }
  - text: "The garage is empty and invites the Owner to add a vehicle"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
      - { entity: owner, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Owner taps Add vehicle, decodes the VIN and saves"
    kind: actor
    capability: add-vehicle
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product adds the vehicle"
    kind: product
    capability: add-vehicle
    actor: owner
    entities:
      - { entity: vehicle, effect: creates, facts: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos, Engine and drivetrain specs, Body specs, Weights and towing, Manufacturing] }
    contexts: { app: { place: garage-app::vehicle-editor } }
---

# First vehicle after setup

## Trigger

Garage is opened for the first time.

## Outcome

The Owner's first vehicle is in the garage.
