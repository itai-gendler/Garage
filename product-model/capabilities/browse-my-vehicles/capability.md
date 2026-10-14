---
availability:
  - { place: garage-app }
domain: my-vehicles
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/dashboard/DashboardViewModel.kt#DashboardViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/dashboard/DashboardScreen.kt#DashboardScreen }
---

# Browse vehicles

My Vehicles: every vehicle in the garage with its photo, current mileage, average fuel economy, fuel trend and counts of overdue and upcoming reminders, from which the Owner opens a vehicle.
