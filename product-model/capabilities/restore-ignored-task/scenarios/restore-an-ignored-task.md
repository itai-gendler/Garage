---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Restore on an ignored task"
    kind: actor
    actor: owner
    entities:
      - { entity: ignored-task, effect: reads, facts: [Task name] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product returns the task to the schedule and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: ignored-task, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Restore an ignored task

## Trigger

The Owner changes their mind.

## Outcome

The task is suggested and reminded again.
