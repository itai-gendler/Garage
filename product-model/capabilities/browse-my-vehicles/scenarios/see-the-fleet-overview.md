---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "Show Fleet Overview is on"
    kind: condition
    entities:
      - { entity: settings, effect: reads, facts: [Show fleet overview] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Product heads the list with the number of vehicles, the fleet's average fuel economy and its total overdue and due-soon reminders"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Current mileage] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Owner taps the reminder status"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Product opens the schedule of the first vehicle with something due"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# See the fleet overview

## Trigger

The Owner keeps several vehicles.

## Outcome

The Owner sees the whole garage's state at once and can jump to what needs attention.
