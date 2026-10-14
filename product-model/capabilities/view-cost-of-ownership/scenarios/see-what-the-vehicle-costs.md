---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Expenses tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product totals maintenance, fuel and charging costs, and breaks them down by maintenance category, Fuel and EV Charging, largest first"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: reads, facts: [Date, Category, Task, Description, Cost, Mileage] }
      - { entity: fill-up, effect: reads, facts: [Date, Total cost, Volume, Price per volume] }
      - { entity: charging-session, effect: reads, facts: [Date, Total cost, Energy added, Charger speed, Battery start, Battery end] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner opens a category to see its entries"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# See what the vehicle costs

## Trigger

The Owner wants to know what the vehicle has cost.

## Outcome

The Owner sees the total, each category's share and the entries behind it.
