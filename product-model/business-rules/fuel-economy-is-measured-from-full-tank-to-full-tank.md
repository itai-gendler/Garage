---
appliesTo:
  - { type: capability, id: view-fuel-log }
  - { type: capability, id: log-fill-up }
  - { type: entity, id: fill-up }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/fuel/FuelEconomyCalculator.kt#FuelEconomyCalculator }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/FuelRecord.kt#FuelRecord }
---

# Fuel economy is measured only from one full tank to the next

Each full-tank fill-up after the first completes a segment: the distance since the previous full tank divided by all fuel bought in between, partial fill-ups included. Average economy is total distance over total fuel, not an average of segments.

## Rationale

A partial fill-up cannot say how much fuel was already in the tank.
