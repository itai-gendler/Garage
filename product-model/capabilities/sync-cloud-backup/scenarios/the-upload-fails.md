---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner taps Sync now"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The server rejects the upload or cannot be reached"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product records and shows why it failed"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Last cloud sync error] }
    contexts: { app: { place: garage-app::settings } }
---

# The upload fails

## Trigger

The server is unavailable.

## Outcome

Settings shows the error; a failed scheduled upload is retried later.
