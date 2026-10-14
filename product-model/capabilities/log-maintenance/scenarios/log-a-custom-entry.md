---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner picks a category, leaves the task as Other / custom, describes the work and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the record without a task"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Description, Cost, Inspected only] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log a custom entry

## Trigger

The work is not one of the built-in tasks.

## Outcome

The record is on the timeline; it satisfies a task only where its category and description match that task.
