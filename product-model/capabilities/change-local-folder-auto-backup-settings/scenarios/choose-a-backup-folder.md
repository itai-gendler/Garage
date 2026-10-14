---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens Local Folder Auto-Backup and taps Select Folder"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner picks a folder on the phone"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the folder, turns auto-backup on and writes a first backup there"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Backup folder, Local folder auto-backup, Last local backup, Last local backup error] }
    contexts: { app: { place: garage-app::settings } }
---

# Choose a backup folder

## Trigger

The Owner wants continuous copies of the garage on the phone.

## Outcome

garage-backup.zip is in the chosen folder and is rewritten after later changes.
