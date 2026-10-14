---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner opens the reading and leaves it empty or zero"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app } }
  - text: "Save stays unavailable until a reading above zero is entered"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app } }
---

# A reading is required

## Trigger

No reading is given.

## Outcome

Nothing is recorded.
