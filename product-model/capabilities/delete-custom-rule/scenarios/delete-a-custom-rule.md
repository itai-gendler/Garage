---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete on a custom rule"
    kind: actor
    actor: owner
    entities:
      - { entity: custom-rule, effect: reads, facts: [Task name] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product removes the rule and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: custom-rule, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete a custom rule

## Trigger

The rule is no longer wanted.

## Outcome

The task disappears, or falls back to the built-in interval of the same name.
