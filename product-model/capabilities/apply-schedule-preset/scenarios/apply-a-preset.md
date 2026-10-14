---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens Schedule Presets from Add custom rule and picks a preset, seeing its included rules"
    kind: actor
    actor: owner
    entities:
      - { entity: custom-rule, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner taps Apply"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds each of the preset's tasks as a custom rule and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: custom-rule, effect: creates, facts: [Task name, Category, Distance interval, Month interval, Notes] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Apply a preset

## Trigger

The vehicle's use matches a common pattern.

## Outcome

The preset's tasks are among the vehicle's custom rules.
