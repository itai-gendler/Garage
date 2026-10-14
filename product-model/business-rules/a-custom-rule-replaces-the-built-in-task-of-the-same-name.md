---
appliesTo:
  - { type: capability, id: add-custom-rule }
  - { type: capability, id: apply-schedule-preset }
  - { type: capability, id: view-maintenance-schedule }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceRule.kt#MaintenanceRule }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleEngine.kt#MaintenanceScheduleEngine }
---

# A custom rule replaces any built-in task with the same name

Tasks are told apart by name, ignoring case. Where several apply to a vehicle, the Owner's custom rule wins; among built-in tasks, the one matching more of make, model and drivetrain wins. Each task therefore appears once.
