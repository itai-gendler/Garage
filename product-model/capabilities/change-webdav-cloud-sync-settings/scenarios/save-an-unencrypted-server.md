---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner enters a server URL that does not start with https:// and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product warns that the connection is unencrypted and suggests a private VPN"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner taps Continue"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the connection and schedules the daily upload"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [WebDAV cloud sync, WebDAV server URL, WebDAV username, WebDAV password] }
    contexts: { app: { place: garage-app::settings } }
---

# Save an unencrypted server

## Trigger

The server is reached over plain http.

## Outcome

The connection is saved only after the Owner continues past the warning; Cancel keeps the previous settings.
