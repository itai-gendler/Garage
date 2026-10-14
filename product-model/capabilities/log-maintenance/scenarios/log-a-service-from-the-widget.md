---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Log Service on a home screen widget"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::garage-widget } }
  - text: "The Product opens the timeline of the default vehicle, or, with none chosen, the first vehicle on My Vehicles, with the form open"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: reads, facts: [Default vehicle] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner fills the form and taps Save"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product adds the record and checks reminders again"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: creates, facts: [Date, Mileage, Category, Task, Description, Cost, Inspected only] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Log a service from the widget

## Trigger

The Owner wants to log a service without finding the vehicle.

## Outcome

The record is on the default vehicle's timeline.
