---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens WebDAV Cloud Sync, switches Enable cloud sync on and enters an https server URL, username and password"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the connection, keeping the password encrypted, and schedules a daily upload while the phone is online"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [WebDAV cloud sync, WebDAV server URL, WebDAV username, WebDAV password] }
    contexts: { app: { place: garage-app::settings } }
---

# Turn on cloud sync

## Trigger

The Owner wants off-phone backups on their own server.

## Outcome

A backup is uploaded to the server once a day.

## Edge cases

- Leaving the password empty when one is saved keeps the saved password.
