---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner fills the form without a make"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "Save stays unavailable until a make is entered"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
---

# A make is required

## Trigger

The make is left blank.

## Outcome

No vehicle is added until it has a make.
