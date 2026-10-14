---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete Emissions & Smog Info in the documents editor and confirms"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product removes that section and keeps the rest"
    kind: product
    actor: owner
    entities:
      - { entity: emissions-test, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete emissions test

## Trigger

The vehicle no longer has this emissions test.

## Outcome

The section is gone from the Documents tab and is no longer reminded.
