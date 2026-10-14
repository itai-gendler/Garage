---
appliesTo:
  - { type: capability, id: log-maintenance }
  - { type: capability, id: view-maintenance-schedule }
  - { type: capability, id: send-maintenance-reminders }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleEngine.kt#MaintenanceScheduleEngine }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/MaintenanceRecord.kt#MaintenanceRecord }
---

# A maintenance record counts toward the task it names

A record with a task satisfies that task, and any tire rotation satisfies a rotation task. A record with no task satisfies a task only when it has the task's category and its description mentions the task or its key words, so logging one fluid service never restarts every other fluid task.
