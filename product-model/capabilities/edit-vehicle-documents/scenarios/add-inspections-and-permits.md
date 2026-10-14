---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner fills in the state inspection, emissions test, inspection sticker or toll pass sections and taps Save Vehicle Documents"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
      - { entity: toll-pass, effect: reads, facts: [] }
      - { entity: inspection-sticker, effect: reads, facts: [] }
      - { entity: emissions-test, effect: reads, facts: [] }
      - { entity: state-inspection, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product keeps each section that was filled in"
    kind: product
    actor: owner
    entities:
      - { entity: state-inspection, effect: creates, facts: [Expiration, Last inspected, Result, Notes] }
      - { entity: emissions-test, effect: creates, facts: [Expiration, Last tested, Result, Notes] }
      - { entity: inspection-sticker, effect: creates, facts: [Expiration, Sticker number, Notes] }
      - { entity: toll-pass, effect: creates, facts: [Expiration, Account, Notes] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Add inspections and permits

## Trigger

The vehicle's state requires inspections or the Owner uses a toll pass.

## Outcome

Each section appears on the Documents tab with its expiration reminded.
