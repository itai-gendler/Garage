---
kind: primary
routes:
  app: Garage app
steps:
  - text: "A day has passed since the last scheduled upload, cloud sync is on and the phone is online"
    kind: condition
    unattended: true
    entities:
      - { entity: settings, effect: reads, facts: [WebDAV cloud sync, WebDAV server URL, WebDAV username] }
    contexts: { app: { place: garage-app } }
  - text: "The Product uploads a fresh backup to the server and records when"
    kind: product
    entities:
      - { entity: settings, effect: changes, facts: [Last cloud sync, Last cloud sync error] }
    contexts: { app: { place: garage-app } }
---

# Daily upload

## Trigger

The daily schedule comes round.

## Outcome

The server copy is at most about a day old.
