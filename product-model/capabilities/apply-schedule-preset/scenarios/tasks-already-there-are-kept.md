---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The vehicle already has a custom rule named like one of the preset's tasks"
    kind: condition
    entities:
      - { entity: custom-rule, effect: reads, facts: [Task name] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner applies the preset"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds only the tasks the vehicle has no custom rule for"
    kind: product
    actor: owner
    entities:
      - { entity: custom-rule, effect: creates, facts: [Task name, Category, Distance interval, Month interval, Notes] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Tasks already there are kept

## Trigger

A preset is applied twice, or over the Owner's own rules.

## Outcome

Existing rules are untouched and no task is duplicated.
