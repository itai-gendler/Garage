---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner taps Export backup and chooses a location"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The destination cannot be opened for writing"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product reports that the export failed and why"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# The file cannot be written

## Trigger

The chosen location is not writable.

## Outcome

No backup is saved; the garage is unchanged.
