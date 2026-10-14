---
relations:
  - entity: maintenance-record
    verb: has
    cardinality: one-to-many
  - entity: fill-up
    verb: has
    cardinality: one-to-many
  - entity: charging-session
    verb: has
    cardinality: one-to-many
  - entity: custom-rule
    verb: has
    cardinality: one-to-many
  - entity: ignored-task
    verb: has
    cardinality: one-to-many
  - entity: recall
    verb: has
    cardinality: one-to-many
  - entity: modification
    verb: has
    cardinality: one-to-many
  - entity: registration
    verb: has
    cardinality: one-to-one
  - entity: state-inspection
    verb: has
    cardinality: one-to-one
  - entity: emissions-test
    verb: has
    cardinality: one-to-one
  - entity: inspection-sticker
    verb: has
    cardinality: one-to-one
  - entity: insurance-policy
    verb: has
    cardinality: one-to-one
  - entity: toll-pass
    verb: has
    cardinality: one-to-one
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/Vehicle.kt#Vehicle }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/VehicleSpecs.kt#VehicleSpecs }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/VehiclePartsInfo.kt#VehiclePartsInfo }
---

# Vehicle

A car, truck or motorcycle the Owner keeps in the garage, with its identity, photos, the specs decoded from its VIN and the Owner's own parts and fluids cheat sheet.

## Information kept

- **VIN** — the 17-character vehicle identification number, if known
- **Year** — model year
- **Make** — manufacturer brand, such as Toyota
- **Model** — model name, such as Tacoma
- **Trim** — trim level
- **Drivetrain** — Unknown, FWD, RWD, AWD or 4WD
- **Fuel type** — primary fuel, decoded or chosen by the Owner
- **Purchased new** — whether the vehicle was bought new or used
- **Initial mileage** — the odometer reading when it joined the garage
- **Photos** — up to three photos, each with the Owner's chosen framing
- **Current mileage** — the highest odometer reading recorded for the vehicle
- **Engine and drivetrain specs** — cylinders, displacement, horsepower, transmission style and speeds, secondary fuel and electrification level, as decoded
- **Body specs** — body class, doors, vehicle type and series, as decoded
- **Weights and towing** — GVWR, GCWR, curb weight and braked and unbraked towing capacity, as decoded
- **Manufacturing** — manufacturer and assembly plant, as decoded
- **Oil** — oil viscosity, capacity and oil filter part number
- **Ignition** — spark plug part number and gap
- **Filters** — engine and cabin air filter part numbers
- **Tires** — front and rear tire size and pressure
- **Wipers** — driver, passenger and rear wiper blade sizes
