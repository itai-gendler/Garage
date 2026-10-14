---
entities:
  - entity: vehicle
    shows: [Year, Make, Model]
  - entity: settings
    shows: [Default vehicle]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/widget/GarageWidget.kt#GarageWidget }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/widget/QuickActionsWidget.kt#QuickActionsWidget }
---

# Garage widget

The home screen widget listing overdue and upcoming maintenance across the garage, the default vehicle's most recent fuel economy, and quick actions to log fuel, update the odometer or log a service.
