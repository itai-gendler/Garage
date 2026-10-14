---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner taps Backup to Folder Now"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The folder is gone, not writable, or access to it was withdrawn"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product records and shows why the backup failed"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Last local backup error] }
    contexts: { app: { place: garage-app::settings } }
---

# The folder can no longer be written

## Trigger

The chosen folder is unavailable.

## Outcome

No backup is written; Settings shows the error and asks the Owner to re-select the folder where access was lost.
