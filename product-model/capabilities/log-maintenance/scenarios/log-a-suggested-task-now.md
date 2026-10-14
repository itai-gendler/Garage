---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Log now on a suggested task"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product opens the form with that task's category, task and description, today's date and the current mileage"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Current mileage] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner enters the cost and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the record and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost, Inspected only] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log a suggested task now

## Trigger

A suggested task has just been done.

## Outcome

The suggestion moves to its next due point.
