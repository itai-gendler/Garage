---
kind: primary
routes:
  app: Garage app
steps:
  - text: "Cloud sync is on with a server, username and password"
    kind: condition
    entities:
      - { entity: settings, effect: reads, facts: [WebDAV cloud sync, WebDAV server URL, WebDAV username] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner taps Sync now"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product uploads a fresh backup to the server, replacing the previous one, and records when"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Last cloud sync, Last cloud sync error] }
    contexts: { app: { place: garage-app::settings } }
---

# Sync now

## Trigger

The Owner wants the server copy up to date now.

## Outcome

The server holds a current garage-backup.zip and Settings shows the sync time.
