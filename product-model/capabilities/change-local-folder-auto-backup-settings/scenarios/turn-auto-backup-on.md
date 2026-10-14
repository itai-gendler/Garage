---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner switches Enable auto-backup on"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the switch and writes a backup to the chosen folder"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Local folder auto-backup, Last local backup, Last local backup error] }
    contexts: { app: { place: garage-app::settings } }
---

# Turn auto-backup on

## Trigger

The Owner resumes folder backups.

## Outcome

A fresh backup is written straight away.
