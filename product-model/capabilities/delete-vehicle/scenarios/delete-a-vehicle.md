---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete vehicle in the vehicle editor and confirms"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product deletes the vehicle, its photos and everything recorded for it, and checks reminders"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: removes }
      - { entity: maintenance-record, effect: removes, with: vehicle }
      - { entity: fill-up, effect: removes, with: vehicle }
      - { entity: charging-session, effect: removes, with: vehicle }
      - { entity: custom-rule, effect: removes, with: vehicle }
      - { entity: ignored-task, effect: removes, with: vehicle }
      - { entity: modification, effect: removes, with: vehicle }
      - { entity: registration, effect: removes, with: vehicle }
      - { entity: state-inspection, effect: removes, with: vehicle }
      - { entity: emissions-test, effect: removes, with: vehicle }
      - { entity: inspection-sticker, effect: removes, with: vehicle }
      - { entity: insurance-policy, effect: removes, with: vehicle }
      - { entity: toll-pass, effect: removes, with: vehicle }
    contexts: { app: { place: garage-app::vehicle-editor } }
  - text: "The Product returns to My Vehicles"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
---

# Delete a vehicle

## Trigger

The Owner no longer has the vehicle.

## Outcome

The vehicle and all its history are gone; its reminders stop.

## Edge cases

- The confirmation names the vehicle and warns that its records go with it.
