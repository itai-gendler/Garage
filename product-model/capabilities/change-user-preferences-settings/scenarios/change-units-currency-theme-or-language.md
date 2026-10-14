---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner picks a new language, measurement system, currency or theme"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves it and shows every distance, volume, economy figure and amount in the new choice"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Language, Units, Currency, Theme] }
    contexts: { app: { place: garage-app::settings } }
---

# Change units, currency, theme or language

## Trigger

The Owner wants Garage to read differently.

## Outcome

Every screen, widget and report uses the new choice; recorded values are not changed.

## Edge cases

- Switching units converts what is shown, because distances and volumes are kept in miles and US gallons.
- Switching currency changes only the symbol shown.
