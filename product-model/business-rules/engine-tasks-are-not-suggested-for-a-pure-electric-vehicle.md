---
appliesTo:
  - { type: capability, id: view-maintenance-schedule }
  - { type: entity, id: vehicle }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleRules.kt#MaintenanceScheduleRules }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/Vehicle.kt#Vehicle }
---

# Engine tasks are not suggested for a pure electric vehicle

Engine oil, power steering fluid, engine air filter, automatic transmission fluid, coolant, spark plugs and the serpentine belt are left out of a battery electric vehicle's schedule. A vehicle counts as purely electric from its decoded fuel and electrification, or, failing that, from well-known electric makes and models.
