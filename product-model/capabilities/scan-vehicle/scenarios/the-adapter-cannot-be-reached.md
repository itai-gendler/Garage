---
kind: edge
routes:
  app: Garage app
steps:
  - text: "The Owner opens the scanner"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product cannot connect to the adapter or loses it mid-scan"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
  - text: "The Product shows the connection as lost with the reason, keeping anything already read"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::obd2-scanner } }
---

# The adapter cannot be reached

## Trigger

The adapter is unplugged, off or out of range.

## Outcome

The Owner can reconnect or change the adapter.
