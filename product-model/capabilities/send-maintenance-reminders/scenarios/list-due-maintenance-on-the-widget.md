---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "A check finishes, or a fill-up, odometer reading or default vehicle changes"
    kind: condition
    unattended: true
    entities:
      - { entity: vehicle, effect: reads, facts: [Year, Make, Model] }
    contexts: { app: { place: garage-app } }
  - text: "The Product lists overdue tasks, then upcoming ones, across the garage on the Garage widget with when each is due, and the default vehicle's most recent fuel economy"
    kind: product
    entities:
      - { entity: settings, effect: reads, facts: [Default vehicle] }
      - { entity: fill-up, effect: reads, facts: [Odometer, Volume, Full tank] }
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::garage-widget } }
---

# List due maintenance on the widget

## Trigger

Something that changes what is due happens.

## Outcome

The widget shows what is due, or All caught up! when nothing is.
