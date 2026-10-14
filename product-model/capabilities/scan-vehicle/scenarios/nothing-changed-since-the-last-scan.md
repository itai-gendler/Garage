---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner taps Rescan"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product reads the vehicle again"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The findings match the last logged scan and the odometer has not passed the current mileage"
    kind: condition
    entities:
      - { entity: maintenance-record, effect: reads, facts: [Task, Description] }
      - { entity: vehicle, effect: reads, facts: [Current mileage] }
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product shows the results and says the scan was not logged again"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# Nothing changed since the last scan

## Trigger

The Owner scans repeatedly.

## Outcome

The timeline gains no duplicate entry.
