---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner picks This Year, Last Year, 12 Months or 6 Months"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product counts only entries dated in that period"
    kind: product
    actor: owner
    entities:
      - { entity: maintenance-record, effect: reads, facts: [Date, Cost] }
      - { entity: fill-up, effect: reads, facts: [Date, Total cost] }
    contexts: { app: { place: garage-app::vehicle } }
---

# Narrow to a period

## Trigger

The Owner wants a yearly or recent figure.

## Outcome

Totals and breakdown cover the chosen period; All Time returns to everything.
