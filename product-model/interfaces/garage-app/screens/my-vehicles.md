---
entities:
  - entity: vehicle
    shows: [Year, Make, Model, Trim, Photos, Current mileage]
  - entity: settings
    shows: [Show fuel trend graph, Show fleet overview]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/dashboard/DashboardScreen.kt#DashboardScreen }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/components/VehicleCard.kt#VehicleCard }
---

# My Vehicles

The garage at a glance: every vehicle with its photo, current mileage, average fuel economy, fuel trend and how many tasks are overdue or due soon, optionally headed by the fleet overview.
