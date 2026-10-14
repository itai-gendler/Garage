---
appliesTo:
  - { type: capability, id: send-renewal-reminders }
  - { type: capability, id: change-reminders-and-expirations-settings }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/DocumentExpirationEngine.kt#DocumentExpirationEngine }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/ReminderCheckWorker.kt#ReminderCheckWorker }
---

# A document or license is due for renewal within the document notice window and overdue from its expiration date

Registration, state inspection, emissions test, inspection sticker, insurance policy, toll pass and the Owner's driver's license each count from their own expiration. The window is 30 days until the Owner changes it, and the reminders stop while document renewal reminders are off.
