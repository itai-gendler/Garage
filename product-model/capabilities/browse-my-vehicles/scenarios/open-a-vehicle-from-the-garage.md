---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens Garage"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Product lists each vehicle, newest first, with its photo, current mileage, average fuel economy, fuel trend and overdue and due-soon counts"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model, Trim, Photos, Current mileage] }
      - { entity: fill-up, effect: reads, facts: [Odometer, Volume, Full tank] }
      - { entity: settings, effect: reads, facts: [Show fuel trend graph, Maintenance mileage notice window, Maintenance time notice window] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Owner taps a vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
    contexts: { app: { place: garage-app::my-vehicles } }
  - text: "The Product opens the vehicle at its timeline"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Open a vehicle from the garage

## Trigger

The Owner opens Garage.

## Outcome

The Owner is looking at the chosen vehicle.

## Edge cases

- Tapping a card's reminder counts opens the vehicle's schedule; tapping its fuel graph opens its fuel log.
- With no vehicles yet the list invites the Owner to add the first one.
