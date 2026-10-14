---
availability:
  - { place: garage-app }
domain: schedule
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/schedule/MaintenanceScheduleTemplates.kt#MaintenanceScheduleTemplates }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/ApplyTemplateSheet.kt#ApplyTemplateSheet }
---

# Apply schedule preset

Adds a ready-made set of custom rules to a vehicle: Heavy Duty & Towing, Daily Commuter, Hybrid & Electric Vehicle (EV) or High Mileage & Classic Car.
