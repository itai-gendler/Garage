---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete and confirms"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::drivers-license } }
  - text: "The Product removes the license and its reminder"
    kind: product
    actor: owner
    entities:
      - { entity: drivers-license, effect: removes }
    contexts: { app: { place: garage-app::drivers-license } }
---

# Delete the license

## Trigger

The Owner no longer wants it kept.

## Outcome

The tab is empty again.
