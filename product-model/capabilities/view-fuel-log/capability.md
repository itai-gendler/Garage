---
availability:
  - { place: garage-app }
domain: fuel
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/fuel/FuelViewModel.kt#FuelViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/fuel/FuelEconomyCalculator.kt#FuelEconomyCalculator }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/fuel/ChargingCalculator.kt#ChargingCalculator }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/fuel/TrendStats.kt#TrendStats }
---

# View fuel log

The Fuel tab: fill-ups with the fuel economy each full tank achieved, average, best and worst economy, total spent and a trend chart; for electric and plug-in hybrid vehicles, charging sessions with efficiency and battery health.
