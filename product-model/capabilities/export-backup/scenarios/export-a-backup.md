---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Export backup and chooses where to save the zip"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product writes a complete copy of the garage's records and photos to the zip and confirms it"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# Export a backup

## Trigger

The Owner wants a copy of the garage, for example to move to a new phone.

## Outcome

A zip holding the whole garage is saved where the Owner chose.

## Edge cases

- Settings, including the cloud and adapter choices, are not part of the backup.
