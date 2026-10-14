---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete Insurance Policy Info in the documents editor and confirms"
    kind: actor
    actor: owner
    entities:
      - { entity: insurance-policy, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product removes that section and keeps the rest"
    kind: product
    actor: owner
    entities:
      - { entity: insurance-policy, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete insurance policy

## Trigger

The vehicle no longer has this insurance policy.

## Outcome

The section is gone from the Documents tab and is no longer reminded.
