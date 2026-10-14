---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner types a VIN"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product asks NHTSA, which returns an error, no details, or cannot be reached"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product shows why and leaves the form as it was"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle-editor } }
---

# The VIN cannot be decoded

## Trigger

NHTSA cannot decode the VIN.

## Outcome

The Owner can correct the VIN, retry, or fill the form by hand.
