---
appliesTo:
  - { type: entity, id: vehicle }
  - { type: capability, id: update-odometer }
  - { type: capability, id: browse-my-vehicles }
  - { type: capability, id: log-fill-up }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/dao/MaintenanceDao.kt#MaintenanceDao }
---

# A vehicle's current mileage is its highest recorded odometer reading

Current mileage is the highest mileage among the vehicle's maintenance records, fuel fill-ups and charging sessions; it is never typed in on its own. A reading lower than an earlier one is kept but does not lower it.
