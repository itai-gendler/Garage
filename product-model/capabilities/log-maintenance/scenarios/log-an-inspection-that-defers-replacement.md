---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner picks a task that can be deferred, such as Brake pad replacement, and ticks Inspected only (defer replacement)"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product turns replace into inspect in the description and asks when to remind again"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner enters both a distance and a number of months to remind in, and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the record as an inspection"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost, Inspected only, Remind in distance, Remind in months] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log an inspection that defers replacement

## Trigger

A part was checked and still has life left.

## Outcome

The task falls due again after the chosen distance or months, whichever comes first, rather than its full interval.
