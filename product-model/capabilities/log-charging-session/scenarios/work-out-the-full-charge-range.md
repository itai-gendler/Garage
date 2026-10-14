---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner enters the battery percentage at the end and the range the car shows, and taps Auto-Calculate"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product fills in the estimated range at 100%"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner saves the session"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product records the session with its full-charge range for battery health"
    kind: product
    actor: owner
    entities:
      - { entity: charging-session, effect: creates, facts: [Date, Odometer, Energy added, Charger speed, Battery start, Battery end, Total cost, Vendor, Vendor type, Range at full charge] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Work out the full-charge range

## Trigger

The Owner wants to track battery health.

## Outcome

Battery health compares this range with the first one recorded.
