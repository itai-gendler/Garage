---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens the Specs tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product shows the decoded engine and drivetrain, weights and towing, body and manufacturing details"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Engine and drivetrain specs, Body specs, Weights and towing, Manufacturing, Fuel type] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Read the decoded specs

## Trigger

The Owner needs a spec such as towing capacity.

## Outcome

The decoded specs are on screen, grouped.
