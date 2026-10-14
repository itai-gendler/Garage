---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps OBD2 Scanner on the vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "An adapter is saved and Garage has the Bluetooth permission it needs"
    kind: condition
    entities:
      - { entity: settings, effect: reads, facts: [OBD2 adapter] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product connects, detects the vehicle's protocol and reads readiness, trouble codes, freeze frame, odometer, distance since codes were cleared, VIN and sensor readings"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product compares the VIN the car reports with the vehicle's"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [VIN] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product logs the scan on the timeline as an OBD2 Scan at the odometer it read"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Scan and log the vehicle

## Trigger

The Owner wants to know why the check engine light is on, or whether the car is ready for a smog test.

## Outcome

The Owner sees the vehicle's health; the scan is on its timeline and its readiness shows on the Documents tab.

## Edge cases

- A reading the car does not answer is skipped rather than ending the scan.
- Rescan runs the scan again.
