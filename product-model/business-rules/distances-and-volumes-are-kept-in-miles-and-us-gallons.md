---
appliesTo:
  - { type: capability, id: change-user-preferences-settings }
  - { type: entity, id: vehicle }
  - { type: entity, id: fill-up }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/util/UnitConverter.kt#UnitConverter }
---

# Distances, volumes and intervals are kept in miles and US gallons and shown in the chosen units

Metric entries are converted when saved and converted back when shown, so switching units never changes what was recorded.
