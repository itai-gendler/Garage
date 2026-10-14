---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete State Inspection Info in the documents editor and confirms"
    kind: actor
    actor: owner
    entities:
      - { entity: state-inspection, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product removes that section and keeps the rest"
    kind: product
    actor: owner
    entities:
      - { entity: state-inspection, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete state inspection

## Trigger

The vehicle no longer has this state inspection.

## Outcome

The section is gone from the Documents tab and is no longer reminded.
