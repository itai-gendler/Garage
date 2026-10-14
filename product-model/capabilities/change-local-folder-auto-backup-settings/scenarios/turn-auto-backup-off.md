---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner switches Enable auto-backup off"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the switch"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Local folder auto-backup] }
    contexts: { app: { place: garage-app::settings } }
---

# Turn auto-backup off

## Trigger

The Owner no longer wants folder backups.

## Outcome

Changes no longer write a backup; the folder and the last backup stay.
