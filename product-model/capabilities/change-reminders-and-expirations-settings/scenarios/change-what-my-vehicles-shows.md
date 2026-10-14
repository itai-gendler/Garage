---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner switches Show Fuel Trend Graph or Show Fleet Overview"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the switch"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Show fuel trend graph, Show fleet overview] }
    contexts: { app: { place: garage-app::settings } }
---

# Change what My Vehicles shows

## Trigger

The Owner wants a busier or calmer garage list.

## Outcome

My Vehicles shows or hides the fuel sparklines and the fleet summary.
