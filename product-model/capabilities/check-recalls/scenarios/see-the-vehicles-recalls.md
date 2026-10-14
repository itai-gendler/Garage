---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Recalls tab"
    kind: actor
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product asks NHTSA for recalls matching the vehicle's model year, make and model"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product lists each campaign with its component, summary, consequence, remedy, report date, park-it and park-outside advice and its status, open ones first"
    kind: product
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [Campaign number, Component, Summary, Consequence, Remedy, Reported date, Park it, Park outside] }
    contexts: { app: { place: garage-app::vehicle } }
---

# See the vehicle's recalls

## Trigger

The Owner wants to know about safety recalls.

## Outcome

The Owner sees every campaign NHTSA lists for the model and where each stands for this vehicle.

## Edge cases

- Campaigns NHTSA lists without a campaign number are left out.
- Every campaign is Open until the Owner says otherwise.
