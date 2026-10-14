---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps the edit button on the Parts tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner fills in oil, ignition, filter, tire and wiper details and saves"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::parts-and-fluids-editor } }
  - text: "The Product saves the cheat sheet"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: changes, facts: [Oil, Ignition, Filters, Tires, Wipers] }
    contexts: { app: { place: garage-app::parts-and-fluids-editor } }
---

# Fill in the cheat sheet

## Trigger

The Owner knows the vehicle's exact parts.

## Outcome

The Parts tab shows the Owner's values instead of estimates.
