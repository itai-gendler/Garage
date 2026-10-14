---
kind: alternative
routes:
  app: Garage app
steps:
  - text: "The Owner taps Re-run Setup in Settings"
    kind: actor
    actor: owner
    entities:
      - { entity: settings, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::settings } }
  - text: "The Owner changes the measurement system, currency or affiliate-link choice and taps Get Started"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::setup } }
  - text: "The Product saves the choices"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Units, Currency, Affiliate links, Setup completed] }
    contexts: { app: { place: garage-app::setup } }
---

# Re-run setup from Settings

## Trigger

The Owner wants to go through setup again.

## Outcome

The new choices apply everywhere; nothing already recorded changes.
