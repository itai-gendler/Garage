---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner picks a backup made by a newer version of Garage"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product refuses it before touching anything and asks the Owner to update the app first"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# A backup from a newer Garage is refused

## Trigger

The backup is newer than the installed app.

## Outcome

Nothing is replaced.
