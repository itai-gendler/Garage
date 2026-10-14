---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Update Odometer on a widget, launcher shortcut or Quick Settings tile"
    kind: actor
    actor: owner
    entities:
      - { entity: settings, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::garage-widget } }
  - text: "The Product opens the reading for the default vehicle, or, with none chosen, the first vehicle on My Vehicles"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: reads, facts: [Default vehicle] }
      - { entity: vehicle, effect: reads, facts: [Current mileage] }
    contexts: { app: { place: garage-app } }
  - text: "The Owner keeps or switches the vehicle, enters the reading and saves"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
  - text: "The Product adds an Odometer Check-in to that vehicle's timeline"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
---

# Update the odometer from a shortcut

## Trigger

The Owner is in the car and wants to log mileage quickly.

## Outcome

The reading is recorded without opening the vehicle.
