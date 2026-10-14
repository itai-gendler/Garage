---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Schedule tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product works out each applicable task from the built-in intervals, the vehicle's custom rules and its records, leaving out ignored tasks"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Make, Model, Drivetrain, Current mileage] }
      - { entity: maintenance-record, effect: reads, facts: [Date, Mileage, Category, Task, Description, Inspected only, Remind in distance, Remind in months] }
      - { entity: custom-rule, effect: reads, facts: [Task name, Category, Distance interval, Month interval, Notes] }
      - { entity: ignored-task, effect: reads, facts: [Task name] }
      - { entity: settings, effect: reads, facts: [Maintenance mileage notice window, Maintenance time notice window] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product lists the Owner's custom rules, then the tasks Overdue first, then Upcoming, then OK, each with when it was last done and when it is due, then the ignored tasks"
    kind: product
    actor: owner
    entities:
      - { entity: ignored-task, effect: reads, facts: [] }
      - { entity: custom-rule, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# See what is due

## Trigger

The Owner wants to know what the vehicle needs.

## Outcome

The Owner sees every task's status and can log, ignore or restore from here.

## Edge cases

- Make-, model- and drivetrain-specific tasks, such as transfer case fluid on 4WD and AWD vehicles, appear only for vehicles they match.
- With no tasks, custom rules or ignored tasks the tab asks the Owner to log some maintenance and mileage.
