---
appliesTo:
  - { type: capability, id: ignore-task }
  - { type: capability, id: view-maintenance-schedule }
  - { type: capability, id: send-maintenance-reminders }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/IgnoredMaintenanceRule.kt#IgnoredMaintenanceRule }
---

# An ignored task is neither suggested nor reminded for its vehicle

Ignoring is per vehicle and by task name; other vehicles keep the task.
