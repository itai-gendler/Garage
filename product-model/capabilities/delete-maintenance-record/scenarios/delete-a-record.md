---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete on a record and confirms"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product deletes the record and its receipt and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete a record

## Trigger

A record should not be there.

## Outcome

The record is gone and the task it satisfied falls back to the previous one.
