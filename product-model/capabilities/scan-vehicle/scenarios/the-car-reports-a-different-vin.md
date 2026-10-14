---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner opens the scanner while plugged into another vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product reads the vehicle and finds its VIN differs from this vehicle's"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [VIN] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product shows the results, says the adapter is connected to a different vehicle and does not log the scan"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# The car reports a different VIN

## Trigger

The adapter is in a different car.

## Outcome

Nothing is added to this vehicle's timeline unless the Owner saves the scan anyway.
