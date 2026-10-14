---
kind: validation
routes:
  app: Garage app
steps:
  - text: "The Owner taps Test connection"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The server refuses the username or password"
    kind: condition
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product reports Authentication failed"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# The credentials are refused

## Trigger

The credentials are wrong.

## Outcome

The Owner is told to check the username and password; other server errors are reported with their status.
