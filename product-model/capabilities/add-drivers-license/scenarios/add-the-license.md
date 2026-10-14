---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Driver's License tab and taps Add Driver's License"
    kind: actor
    actor: owner
    entities:
      - { entity: drivers-license, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::drivers-license } }
  - text: "The Owner enters the expiration, number, issuing state, notes and photos of both sides, and taps Save Driver's License"
    kind: actor
    actor: owner
    entities:
      - { entity: drivers-license, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::drivers-license } }
  - text: "The Product keeps the license and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: drivers-license, effect: creates, facts: [Number, Issuing state, Expiration, Notes, Front photo, Back photo] }
    contexts: { app: { place: garage-app::drivers-license } }
---

# Add the license

## Trigger

The Owner wants the license at hand and its renewal reminded.

## Outcome

The tab shows the license; its expiration is reminded.
