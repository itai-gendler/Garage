---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Add custom rule"
    kind: actor
    actor: owner
    entities:
      - { entity: custom-rule, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner enters a task name, category, a distance interval, a month interval or both, and notes, and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the rule and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: custom-rule, effect: creates, facts: [Task name, Category, Distance interval, Month interval, Notes] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Add a custom interval

## Trigger

The vehicle needs something the built-in tasks do not cover, such as track-day checks.

## Outcome

The task appears under Your custom rules and in the schedule.
