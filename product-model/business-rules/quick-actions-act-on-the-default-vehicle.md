---
appliesTo:
  - { type: capability, id: update-odometer }
  - { type: capability, id: log-fill-up }
  - { type: capability, id: log-maintenance }
  - { type: capability, id: change-user-preferences-settings }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/MainViewModel.kt#MainViewModel }
---

# Quick actions, tiles and widgets act on the default vehicle

Log Fuel, Log Service and Update Odometer open the vehicle chosen as default; with none chosen, or a vehicle that no longer exists, they fall back to another vehicle in the garage.
