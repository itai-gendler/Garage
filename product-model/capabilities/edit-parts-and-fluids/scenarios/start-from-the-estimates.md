---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Auto-fill estimated specs and, after the reminder to verify with the owner's manual, taps Apply & Understand"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::parts-and-fluids-editor } }
  - text: "The Product replaces the oil, spark plug gap, air filter, tire pressure and wiper fields with Garage's estimates"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model, Engine and drivetrain specs] }
    contexts: { app: { place: garage-app::parts-and-fluids-editor } }
  - text: "The Owner corrects what differs and saves"
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

# Start from the estimates

## Trigger

The Owner wants a head start.

## Outcome

The cheat sheet is saved with the estimates the Owner kept.
