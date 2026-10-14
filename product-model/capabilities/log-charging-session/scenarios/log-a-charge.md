---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Add charging session"
    kind: actor
    actor: owner
    entities:
      - { entity: charging-session, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner enters date, odometer, kWh added, charger speed, battery percentages, total cost and where it charged, and saves"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product records the session, refreshes widgets and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: charging-session, effect: creates, facts: [Date, Odometer, Energy added, Charger speed, Battery start, Battery end, Total cost, Vendor, Vendor type, Range at full charge] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log a charge

## Trigger

The Owner has charged the vehicle.

## Outcome

The session is in the charging log and its efficiency is worked out against the previous one.

## Edge cases

- Battery percentages left empty are taken as 20% and 80%.
- A charge at home may cost nothing.
