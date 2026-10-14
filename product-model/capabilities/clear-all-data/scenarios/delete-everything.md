---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Clear All Data and confirms Delete Everything"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product forgets the cloud backup settings and stops scheduled backups and syncs"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [WebDAV cloud sync, WebDAV server URL, WebDAV username, WebDAV password, Last cloud sync, Last cloud sync error, Local folder auto-backup, Backup folder, Last local backup, Last local backup error] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product deletes every vehicle with everything recorded for it, and every stored photo"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: removes }
      - { entity: maintenance-record, effect: removes, with: vehicle }
      - { entity: fill-up, effect: removes, with: vehicle }
      - { entity: charging-session, effect: removes, with: vehicle }
      - { entity: custom-rule, effect: removes, with: vehicle }
      - { entity: ignored-task, effect: removes, with: vehicle }
      - { entity: modification, effect: removes, with: vehicle }
      - { entity: registration, effect: removes, with: vehicle }
      - { entity: state-inspection, effect: removes, with: vehicle }
      - { entity: emissions-test, effect: removes, with: vehicle }
      - { entity: inspection-sticker, effect: removes, with: vehicle }
      - { entity: insurance-policy, effect: removes, with: vehicle }
      - { entity: toll-pass, effect: removes, with: vehicle }
    contexts: { app: { place: garage-app::settings } }
---

# Delete everything

## Trigger

The Owner wants to start over or hand the phone on.

## Outcome

The garage is empty and no backup destination is configured.

## Edge cases

- The confirmation warns that this cannot be undone.
