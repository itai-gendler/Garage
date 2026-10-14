---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Clear Codes and confirms, having been warned it resets emissions readiness"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product asks the vehicle to clear its codes and the vehicle confirms"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product logs OBD2 Codes Cleared on the timeline with the codes that were cleared"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product scans the vehicle again"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Clear the codes

## Trigger

The fault was fixed and the light should go off.

## Outcome

The codes are cleared, the clearing is on the timeline and the fresh scan is shown.

## Edge cases

- Permanent codes cannot be cleared; the vehicle removes them once it verifies the repair.
- When the car reported a different VIN the clearing is not logged.
