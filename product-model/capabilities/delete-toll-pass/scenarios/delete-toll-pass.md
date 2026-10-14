---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete Toll Pass & Parking Info in the documents editor and confirms"
    kind: actor
    actor: owner
    entities:
      - { entity: toll-pass, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product removes that section and keeps the rest"
    kind: product
    actor: owner
    entities:
      - { entity: toll-pass, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete toll pass

## Trigger

The vehicle no longer has this toll pass or parking permit.

## Outcome

The section is gone from the Documents tab and is no longer reminded.
