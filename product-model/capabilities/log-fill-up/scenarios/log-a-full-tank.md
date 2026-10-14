---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Add fuel fill-up"
    kind: actor
    actor: owner
    entities:
      - { entity: fill-up, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner enters the date, odometer reading, volume and total cost, leaving Filled to full tank on, and saves"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product records the fill-up with its price per volume, refreshes widgets and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: fill-up, effect: creates, facts: [Date, Odometer, Volume, Total cost, Price per volume, Full tank] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log a full tank

## Trigger

The Owner has just filled up.

## Outcome

The fill-up is in the log; if it follows another full tank, its economy is shown.
