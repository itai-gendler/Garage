---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner marks individual campaigns open or serviced for the report, or taps All Serviced or All Open"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::service-book-export } }
  - text: "The Product uses those choices in the report's recall section without changing the saved statuses"
    kind: product
    actor: owner
    entities:
      - { entity: recall, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::service-book-export } }
  - text: "The Owner generates the PDF"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::service-book-export } }
---

# Adjust recall status for the report

## Trigger

The saved statuses are out of date for this report.

## Outcome

The report shows the recall status the Owner chose; the Recalls tab is unchanged.
