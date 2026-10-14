---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Log Fuel on a widget, launcher shortcut or Quick Settings tile"
    kind: actor
    actor: owner
    entities:
      - { entity: settings, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::garage-widget } }
  - text: "The Product opens the Fuel tab of the default vehicle, or, with none chosen, the first vehicle on My Vehicles, with the fill-up form open"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: reads, facts: [Default vehicle] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner fills the form and saves"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product records the fill-up"
    kind: product
    actor: owner
    entities:
      - { entity: fill-up, effect: creates, facts: [Date, Odometer, Volume, Total cost, Price per volume, Full tank] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log fuel from a shortcut

## Trigger

The Owner is at the pump.

## Outcome

The fill-up is logged in a few taps.

## Edge cases

- For a pure electric default vehicle the charging session form opens instead.
