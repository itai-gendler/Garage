---
appliesTo:
  - { type: capability, id: apply-schedule-preset }
  - { type: entity, id: custom-rule }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/MaintenanceSuggestionsViewModel.kt#MaintenanceSuggestionsViewModel }
---

# Applying a preset adds only tasks the vehicle has no custom rule for

Tasks are compared by name, ignoring case.
