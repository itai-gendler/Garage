---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Export Maintenance Log on the vehicle"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product checks NHTSA recalls for the vehicle and marks those still open by their saved status"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
      - { entity: recall, effect: reads, facts: [Campaign number, Component] }
    contexts: { app: { place: garage-app::service-book-export } }
  - text: "The Owner chooses whether to include upgrades and modifications, parts and fluid specifications, safety recall status and fuel and charging logs"
    kind: actor
    actor: owner
    entities:
      - { entity: modification, effect: reads, facts: [] }
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::service-book-export } }
  - text: "The Owner taps Generate Vehicle Service Book (PDF) and chooses where to save it"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::service-book-export } }
  - text: "The Product writes the PDF and posts a notification that opens it"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Photos, Engine and drivetrain specs, Oil, Ignition, Filters, Tires, Wipers] }
      - { entity: maintenance-record, effect: reads, facts: [Date, Mileage, Category, Description, Cost] }
      - { entity: modification, effect: reads, facts: [Title, Category, Description, Installation date, Cost] }
    contexts: { app: { place: garage-app::service-book-export } }
---

# Generate the service book

## Trigger

The Owner is selling the vehicle or needs its history on paper.

## Outcome

A paginated Vehicle Service & History Book PDF is saved where the Owner chose.

## Edge cases

- Fuel and charging logs are left out unless chosen.
- The total care investment counts maintenance and, when included, mods; fuel is never part of it.
