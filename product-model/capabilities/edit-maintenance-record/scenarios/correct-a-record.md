---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Edit on a record, changes it and taps Save"
    kind: actor
    actor: owner
    entities:
      - { entity: maintenance-record, effect: reads, facts: [Date, Mileage, Category, Task, Description, Cost] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product saves the record and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: changes, facts: [Date, Mileage, Category, Task, Description, Cost, Inspected only, Remind in distance, Remind in months] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Correct a record

## Trigger

A record was entered wrongly.

## Outcome

The timeline and schedule reflect the corrected record.
