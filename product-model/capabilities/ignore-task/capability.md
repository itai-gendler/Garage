---
availability:
  - { place: garage-app }
domain: schedule
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/MaintenanceSuggestionsViewModel.kt#MaintenanceSuggestionsViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/dao/IgnoredMaintenanceRuleDao.kt#IgnoredMaintenanceRuleDao }
---

# Ignore task

Stops suggesting and reminding a task for one vehicle.
