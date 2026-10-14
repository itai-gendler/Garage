---
kind: primary
routes:
  app: Garage app
steps:
  - text: "Auto-backup is on and a folder is chosen"
    kind: condition
    entities:
      - { entity: settings, effect: reads, facts: [Local folder auto-backup, Backup folder] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner taps Backup to Folder Now"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product writes garage-backup.zip to the folder, replacing the previous one, and records when"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Last local backup, Last local backup error] }
    contexts: { app: { place: garage-app::settings } }
---

# Back up to the folder now

## Trigger

The Owner wants a backup right now.

## Outcome

The folder holds a current backup and Settings shows when it was saved.
