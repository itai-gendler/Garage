---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the vehicle at its Timeline tab"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product lists the vehicle's maintenance records newest first, each with category, description, date, mileage and cost"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: reads, facts: [Category, Description, Date, Mileage, Cost, Receipt] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner taps a record's receipt"
    kind: actor
    actor: owner
    entities:
      - { entity: maintenance-record, effect: reads, facts: [Receipt] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product previews an image receipt, or opens a PDF in another app"
    kind: product
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
---

# Read the history

## Trigger

The Owner wants to see what has been done.

## Outcome

The Owner sees the vehicle's history and any receipt.
