---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Add maintenance record on the timeline"
    kind: actor
    actor: owner
    entities:
      - { entity: maintenance-record, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product opens the form dated today with the vehicle's current mileage filled in"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Current mileage] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner picks a category and one of its tasks, adjusts date and mileage, describes the work, enters the cost and attaches a receipt image or PDF"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the record and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost, Receipt, Inspected only] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log a service

## Trigger

The Owner had work done on the vehicle.

## Outcome

The record is on the timeline and the task it names restarts its interval.
