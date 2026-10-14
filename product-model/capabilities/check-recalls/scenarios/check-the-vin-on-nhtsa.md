---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Check VIN on NHTSA.gov"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [VIN] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product copies the VIN and opens NHTSA's recall lookup in the browser"
    kind: product
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Check the VIN on NHTSA

## Trigger

The Owner wants NHTSA's VIN-specific answer.

## Outcome

The Owner can paste the VIN on NHTSA's site.
