---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The daily check comes round, or a record, rule, vehicle or notice window has just changed"
    kind: condition
    unattended: true
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model, Current mileage] }
      - { entity: maintenance-record, effect: reads, facts: [Date, Mileage, Task, Category, Description] }
      - { entity: custom-rule, effect: reads, facts: [Task name, Distance interval, Month interval] }
      - { entity: ignored-task, effect: reads, facts: [Task name] }
      - { entity: settings, effect: reads, facts: [Maintenance mileage notice window, Maintenance time notice window] }
    contexts: { app: { place: garage-app } }
  - text: "The Product posts one notification per vehicle and task that is Overdue or Upcoming, naming the task and the vehicle"
    kind: product
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
  - text: "The Product withdraws the notification of any task that is no longer due"
    kind: product
    entities: []
    contexts: { app: { place: garage-app } }
---

# Post due maintenance notifications

## Trigger

The schedule or the garage changes.

## Outcome

The Owner has one current notification per due task; tapping it opens that vehicle's schedule.

## Edge cases

- A task keeps a single notification however often the check runs.
