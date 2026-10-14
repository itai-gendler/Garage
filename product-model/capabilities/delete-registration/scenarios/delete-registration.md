---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete Tag & Registration Info in the documents editor and confirms"
    kind: actor
    actor: owner
    entities:
      - { entity: registration, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product removes that section and keeps the rest"
    kind: product
    actor: owner
    entities:
      - { entity: registration, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete registration

## Trigger

The vehicle no longer has this tag and registration.

## Outcome

The section is gone from the Documents tab and is no longer reminded.
