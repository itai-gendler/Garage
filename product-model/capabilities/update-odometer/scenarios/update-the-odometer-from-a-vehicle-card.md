---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps the mileage on a vehicle card"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Product asks for the reading, showing the current mileage"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Current mileage] }
    contexts: { app: { place: garage-app } }
  - text: "The Owner enters the reading, optionally a date and notes, and saves"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app } }
  - text: "The Product adds an Odometer Check-in to the vehicle's timeline, refreshes widgets and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
---

# Update the odometer from a vehicle card

## Trigger

The Owner wants mileage-based reminders to stay accurate.

## Outcome

The vehicle's current mileage reflects the reading, with no cost recorded.

## Edge cases

- Without notes the entry is described as Odometer check-in.
