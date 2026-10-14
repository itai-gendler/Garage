---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner leaves the task name empty, or gives neither a distance nor a month interval"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "Save stays unavailable"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# A name and an interval are required

## Trigger

The rule is incomplete.

## Outcome

No rule is added.
