---
appliesTo:
  - { type: capability, id: view-maintenance-schedule }
  - { type: capability, id: send-maintenance-reminders }
  - { type: capability, id: change-reminders-and-expirations-settings }
  - { type: capability, id: browse-my-vehicles }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleEngine.kt#MaintenanceScheduleEngine }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/PreferencesManager.kt#PreferencesManager }
---

# A task is Upcoming within the notice windows and Overdue once its due point is reached

A task is Overdue when the current mileage has reached its due mileage or today has reached its due date, Upcoming when either is within the maintenance mileage or time notice window, and OK otherwise. The windows are 500 miles and 10 days until the Owner changes them.
