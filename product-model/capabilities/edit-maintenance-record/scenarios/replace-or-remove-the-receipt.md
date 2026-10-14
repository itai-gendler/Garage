---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Change Attachment and picks another image or PDF, or taps Remove Attachment, and saves"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product keeps the new receipt and deletes the one it replaces or the one removed"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: changes, facts: [Receipt] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Replace or remove the receipt

## Trigger

The wrong receipt was attached.

## Outcome

Only the current receipt is kept.
