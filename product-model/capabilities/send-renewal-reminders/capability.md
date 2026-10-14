---
availability:
  - { place: garage-app }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/ReminderCheckWorker.kt#ReminderCheckWorker }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/DocumentExpirationEngine.kt#DocumentExpirationEngine }
---

# Send renewal reminders

Garage notifies the Owner when a vehicle's registration, inspection, emissions test, inspection sticker, insurance policy or toll pass, or the Owner's driver's license, is about to expire or has expired.
