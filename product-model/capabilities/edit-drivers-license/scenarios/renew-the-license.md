---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Edit License, changes the expiration or photos and saves"
    kind: actor
    actor: owner
    entities:
      - { entity: drivers-license, effect: reads, facts: [Expiration, Number] }
    contexts: { app: { place: garage-app::drivers-license } }
  - text: "The Product saves the license and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: drivers-license, effect: changes, facts: [Number, Issuing state, Expiration, Notes, Front photo, Back photo] }
    contexts: { app: { place: garage-app::drivers-license } }
---

# Renew the license

## Trigger

The license was renewed.

## Outcome

The new expiration is reminded instead of the old one.

## Edge cases

- Each detail can be copied from the tab with a tap.
