---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps the edit button on the Documents tab"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner fills in the plate, state, registration expiration and fee, a photo of the card, and the insurer, policy number, expiration, premium and agent contact"
    kind: actor
    actor: owner
    entities:
      - { entity: registration, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Owner taps Save Vehicle Documents"
    kind: actor
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product keeps the registration and insurance policy for the vehicle"
    kind: product
    actor: owner
    entities:
      - { entity: registration, effect: creates, facts: [License plate, State, Expiration, Renewal fee, Notes, Photo] }
      - { entity: insurance-policy, effect: creates, facts: [Provider, Policy number, Expiration, Premium, Agent contact, Notes, Photo] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Add registration and insurance

## Trigger

The Owner wants the paperwork at hand and renewals reminded.

## Outcome

The Documents tab shows both, and their expirations are reminded.
