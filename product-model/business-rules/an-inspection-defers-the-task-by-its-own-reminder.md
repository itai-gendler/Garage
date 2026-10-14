---
appliesTo:
  - { type: capability, id: log-maintenance }
  - { type: capability, id: edit-maintenance-record }
  - { type: capability, id: view-maintenance-schedule }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleEngine.kt#MaintenanceScheduleEngine }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleRules.kt#MaintenanceScheduleRules }
---

# An inspection-only record moves its task's next due point by its own reminder distance and months

Only tasks that can be deferred, such as brakes, tires, belts, filters and wipers, offer Inspected only, and an inspection must give both a distance and a number of months. The task is then due at the inspection's mileage plus that distance, or its date plus those months, instead of the full interval.
