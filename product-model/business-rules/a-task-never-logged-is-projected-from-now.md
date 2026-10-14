---
appliesTo:
  - { type: capability, id: view-maintenance-schedule }
  - { type: capability, id: send-maintenance-reminders }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleEngine.kt#MaintenanceScheduleEngine }
---

# A task never logged falls due at the first multiple of its distance interval at or above the current mileage, and one time interval from today

Without a record to start from, the distance due point is the first multiple of the interval at or beyond the current mileage, and the date due point is the interval counted from today.
