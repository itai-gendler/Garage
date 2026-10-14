---
appliesTo:
  - { type: capability, id: log-charging-session }
  - { type: capability, id: edit-charging-session }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/fuel/FuelScreen.kt#FuelScreen }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/fuel/ChargingCalculator.kt#ChargingCalculator }
---

# A charging session needs an odometer reading, energy added above zero and a total cost, which may be zero

Efficiency compares each session's energy with the distance since the previous session; battery health compares the latest full-charge range with the first one recorded.
