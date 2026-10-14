---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner picks a zip without a Garage database, or with an unreadable one"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product refuses it and says it does not look like a Garage backup"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# A file that is not a Garage backup is refused

## Trigger

The wrong file is picked.

## Outcome

Nothing is replaced.
