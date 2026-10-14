---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Edit on a fill-up, changes it and saves"
    kind: actor
    actor: owner
    entities:
      - { entity: fill-up, effect: reads, facts: [Date, Odometer, Volume, Total cost, Full tank] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product saves it and works the economy out again"
    kind: product
    actor: owner
    entities:
      - { entity: fill-up, effect: changes, facts: [Date, Odometer, Volume, Total cost, Price per volume, Full tank] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Correct a fill-up

## Trigger

A fill-up was entered wrongly.

## Outcome

The log and economy reflect the corrected fill-up.
