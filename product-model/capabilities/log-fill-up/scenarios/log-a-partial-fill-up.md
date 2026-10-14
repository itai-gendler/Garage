---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner enters a fill-up and turns Filled to full tank off"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product records it as partial"
    kind: product
    actor: owner
    entities:
      - { entity: fill-up, effect: creates, facts: [Date, Odometer, Volume, Total cost, Price per volume, Full tank] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log a partial fill-up

## Trigger

The tank was not topped off.

## Outcome

The fill-up shows as Partial; its fuel counts toward the next full tank's economy instead of producing its own.
