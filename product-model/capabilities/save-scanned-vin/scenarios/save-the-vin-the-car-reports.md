---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The vehicle has no VIN and the car reported one"
    kind: condition
    entities:
      - { entity: vehicle, effect: reads, facts: [VIN] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Owner taps Save VIN"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product saves the VIN on the vehicle"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: changes, facts: [VIN] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Save the VIN the car reports

## Trigger

The vehicle was added without a VIN.

## Outcome

The vehicle has its VIN; later scans are matched against it.
