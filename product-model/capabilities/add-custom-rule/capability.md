---
availability:
  - { place: garage-app }
domain: schedule
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/MaintenanceSuggestionsScreen.kt#MaintenanceSuggestionsScreen }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/CustomMaintenanceRule.kt#CustomMaintenanceRule }
---

# Add custom rule

Adds the Owner's own maintenance interval for a vehicle, by distance, by months, or both.
