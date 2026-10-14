---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner enters a server URL and username and taps Test connection"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product asks the server for the folder with those credentials and reports Connection successful"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
---

# The server answers

## Trigger

The Owner wants to know the details are right.

## Outcome

The Owner knows the server accepts the credentials; nothing is saved.
