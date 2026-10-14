---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The last scan was held back because of a VIN mismatch"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Owner taps Save Scan Anyway"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product logs the scan on this vehicle's timeline"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Save a held-back scan

## Trigger

The Owner knows the scan belongs to this vehicle.

## Outcome

The scan is on the timeline.
