---
appliesTo:
  - { type: entity, id: vehicle }
  - { type: capability, id: delete-vehicle }
  - { type: capability, id: clear-all-data }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/MaintenanceRecord.kt#MaintenanceRecord }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/GarageDatabase.kt#GarageDatabase }
---

# Deleting a vehicle deletes everything recorded for it

Its maintenance records, fill-ups, charging sessions, custom rules, ignored tasks, recall statuses, modifications and documents go with it.
