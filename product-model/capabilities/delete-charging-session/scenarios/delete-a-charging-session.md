---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner taps Delete on a charging session and confirms"
    kind: actor
    actor: owner
    entities:
      - { entity: charging-session, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::vehicle } }
  - text: "The Product deletes it"
    kind: product
    actor: owner
    entities:
      - { entity: charging-session, effect: removes }
    contexts: { app: { place: garage-app::vehicle } }
---

# Delete a charging session

## Trigger

A session should not be there.

## Outcome

The session is gone from the log and from the efficiency figures.
