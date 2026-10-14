---
kind: primary
routes:
  app: Garage app
steps:
  - text: "Garage opens for the first time, before setup is completed"
    kind: condition
    entities:
      - { entity: settings, effect: reads, facts: [Setup completed] }
    contexts: { app: { place: garage-app::setup } }
  - text: "The Owner chooses Metric or Imperial units, a language and a currency"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::setup } }
  - text: "The Owner grants notification and camera permissions and decides whether to enable affiliate links"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::setup } }
  - text: "The Owner taps Get Started"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::setup } }
  - text: "The Product saves the choices and marks setup completed"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [Units, Currency, Affiliate links, Setup completed] }
    contexts: { app: { place: garage-app::setup } }
  - text: "The Product opens My Vehicles"
    kind: product
    actor: owner
    entities:
      - { entity: vehicle, effect: reads, facts: [] }
    contexts: { app: { place: garage-app::my-vehicles } }
---

# Finish the first-run setup

## Trigger

Garage is opened for the first time.

## Outcome

Units, currency and the affiliate-link choice are saved, setup is complete, and the Owner lands on My Vehicles.

## Edge cases

- Declining a permission does not stop setup; reminders and the VIN scanner stay unavailable until it is granted.
- The language takes effect at once; it is the phone's per-app language.
