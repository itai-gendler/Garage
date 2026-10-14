---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner changes the insurance policy's expiration and premium after renewing, and saves"
    kind: actor
    actor: owner
    entities:
      - { entity: insurance-policy, effect: reads, facts: [Expiration, Premium] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product saves the new details"
    kind: product
    actor: owner
    entities:
      - { entity: insurance-policy, effect: changes, facts: [Expiration, Premium] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Update a renewed document

## Trigger

A document was renewed.

## Outcome

The new expiration is what the next daily check reminds about.
