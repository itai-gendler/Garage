---
appliesTo:
  - { type: capability, id: view-maintenance-schedule }
  - { type: capability, id: send-maintenance-reminders }
  - { type: capability, id: browse-my-vehicles }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleEngine.kt#MaintenanceScheduleEngine }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceRule.kt#MaintenanceRule }
---

# A maintenance task falls due at its distance or its time interval after it was last done, whichever comes first

The last time a task was done is the record with the highest mileage that satisfies it; its distance and date are both projected from that one record. A task with only one kind of interval is due by that one alone.

## Rationale

Low-mileage vehicles would otherwise never reach a mileage-only interval.
