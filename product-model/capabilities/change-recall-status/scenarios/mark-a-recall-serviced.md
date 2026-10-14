---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens an open recall's status and picks Serviced / Completed"
    kind: actor
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [Campaign number, Component] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product keeps the recall as Serviced for this vehicle and moves it below the open ones"
    kind: product
    actor: owner
    entities:
      - { entity: recall, effect: changes, from: Open, to: Serviced, facts: [] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Mark a recall serviced

## Trigger

The dealer did the recall work.

## Outcome

The recall shows as Serviced whenever the tab is opened.
