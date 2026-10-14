---
kind: primary
routes:
  app: Garage app
steps:
  - text: "A vehicle, its parts and specs, a maintenance record, a fuel fill-up or a custom rule changes while auto-backup is on"
    kind: condition
    unattended: true
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
      - { entity: maintenance-record, effect: reads, facts: [] }
      - { entity: fill-up, effect: reads, facts: [] }
      - { entity: custom-rule, effect: reads, facts: [] }
      - { entity: settings, effect: reads, facts: [Local folder auto-backup, Backup folder] }
    contexts: { app: { place: garage-app } }
  - text: "The Product waits briefly for further changes, then writes garage-backup.zip to the folder and records when"
    kind: product
    entities:
      - { entity: settings, effect: changes, facts: [Last local backup, Last local backup error] }
    contexts: { app: { place: garage-app } }
---

# Back up after a change

## Trigger

The garage changes.

## Outcome

The folder's backup matches the garage within moments of the change.
