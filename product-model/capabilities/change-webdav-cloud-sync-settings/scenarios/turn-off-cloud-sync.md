---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner switches Enable cloud sync off and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the switch and cancels the daily upload"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [WebDAV cloud sync] }
    contexts: { app: { place: garage-app::settings } }
---

# Turn off cloud sync

## Trigger

The Owner stops cloud backups.

## Outcome

No more uploads happen; the server details stay saved.
