---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Ignore on a suggested task"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product moves the task to Ignored tasks for this vehicle and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: ignored-task, effect: creates, facts: [Task name] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Ignore a suggested task

## Trigger

A task does not apply to how the Owner uses the vehicle.

## Outcome

The task is listed as Ignored for this vehicle and is no longer reminded.
