---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner adds a custom rule with the same name as a built-in task, such as Engine oil change, and a shorter interval"
    kind: actor
    actor: owner
    entities:
      - { entity: custom-rule, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the rule"
    kind: product
    actor: owner
    entities:
      - { entity: custom-rule, effect: creates, facts: [Task name, Category, Distance interval, Month interval, Notes] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product schedules that task by the custom interval instead of the built-in one"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# Override a built-in interval

## Trigger

The built-in interval does not suit the vehicle.

## Outcome

The task appears once, due by the Owner's interval.
