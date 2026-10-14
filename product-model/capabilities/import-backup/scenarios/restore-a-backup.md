---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Import backup and picks a Garage backup zip"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product checks the file is a Garage backup it can read"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product replaces all records and photos with the backup's"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product asks the Owner to restart Garage to load the restored data"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner taps Restart now"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# Restore a backup

## Trigger

The Owner is moving their garage to this phone or rolling back.

## Outcome

After the restart the garage is exactly what the backup held.
