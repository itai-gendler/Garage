---
availability:
  - { place: garage-app }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/ReminderCheckWorker.kt#ReminderCheckWorker }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/ReminderNotifier.kt#ReminderNotifier }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/WorkScheduler.kt#WorkScheduler }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/widget/GarageWidget.kt#GarageWidget }
---

# Send maintenance reminders

Garage checks every vehicle's tasks once a day and right after changes, notifies the Owner of anything overdue or upcoming, and keeps the Garage widget's list current.
