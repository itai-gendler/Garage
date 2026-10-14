---
kind: primary
routes:
  app: Garage app
steps:
  - text: "The Owner opens OBD2 Adapter and picks a paired Bluetooth device, one found by a Bluetooth LE scan, or a Wi-Fi adapter"
    kind: actor
    actor: owner
    entities: []
    contexts: { app: { place: garage-app::settings } }
  - text: "The Product saves the adapter"
    kind: product
    actor: owner
    entities:
      - { entity: settings, effect: changes, facts: [OBD2 adapter] }
    contexts: { app: { place: garage-app::settings } }
---

# Select an adapter in Settings

## Trigger

The Owner has an adapter to use.

## Outcome

The scanner connects to this adapter whenever it is opened.

## Edge cases

- Likely OBD2 adapters are listed first.
- A Bluetooth LE scan stops by itself after about twelve seconds.
