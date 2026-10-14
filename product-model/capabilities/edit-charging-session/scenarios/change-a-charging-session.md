---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Edit on a charging session, changes it and saves"
    kind: actor
    actor: owner
    entities:
      - { entity: charging-session, effect: reads, facts: [Date, Odometer, Energy added] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product saves it and works efficiency and battery health out again"
    kind: product
    actor: owner
    entities:
      - { entity: charging-session, effect: changes, facts: [Date, Odometer, Energy added, Charger speed, Battery start, Battery end, Total cost, Vendor, Vendor type, Range at full charge] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Change a charging session

## Trigger

A session was entered wrongly.

## Outcome

The log reflects the corrected session.
