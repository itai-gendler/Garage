---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The daily check comes round with document renewal reminders on"
    kind: condition
    unattended: true
    entities:
      - { entity: registration, effect: reads, facts: [Expiration] }
      - { entity: state-inspection, effect: reads, facts: [Expiration] }
      - { entity: emissions-test, effect: reads, facts: [Expiration] }
      - { entity: inspection-sticker, effect: reads, facts: [Expiration] }
      - { entity: insurance-policy, effect: reads, facts: [Expiration] }
      - { entity: toll-pass, effect: reads, facts: [Expiration] }
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
      - { entity: settings, effect: reads, facts: [Document renewal reminders, Document expiration notice window] }
    contexts: { app: { place: garage-app } }
  - text: "The Product posts a notification for each document expiring within the notice window or already expired, naming the renewal and the vehicle"
    kind: product
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app } }
---

# Remind about expiring documents

## Trigger

A document's expiration approaches.

## Outcome

The Owner is reminded to renew; tapping the notification opens the vehicle's documents.
