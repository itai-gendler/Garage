---
availability:
  - { place: garage-app }
domain: schedule
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/MaintenanceSuggestionsViewModel.kt#MaintenanceSuggestionsViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleEngine.kt#MaintenanceScheduleEngine }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleRules.kt#MaintenanceScheduleRules }
  - { kind: doc, role: intent, target: README.md }
---

# View maintenance schedule

The Schedule tab: every maintenance task that applies to the vehicle, when it was last done, when it is next due by mileage and by date, and whether it is Overdue, Upcoming or OK; with the Owner's custom rules and ignored tasks.
