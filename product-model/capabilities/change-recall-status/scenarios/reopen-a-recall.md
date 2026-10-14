---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner picks Open on a serviced recall"
    kind: actor
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product keeps the recall as Open again"
    kind: product
    actor: owner
    entities:
      - { entity: recall, effect: changes, from: Serviced, to: Open, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Reopen a recall

## Trigger

The status was set by mistake.

## Outcome

The recall is back among the open ones.
