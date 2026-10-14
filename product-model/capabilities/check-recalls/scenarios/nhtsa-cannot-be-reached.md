---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Recalls tab while NHTSA cannot be reached"
    kind: actor
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product shows the error with Retry"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner taps Retry"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# NHTSA cannot be reached

## Trigger

The phone is offline or NHTSA is down.

## Outcome

The Owner can try again; saved statuses are kept.
