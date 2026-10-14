---
availability:
  - { place: garage-app }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/MaintenanceTimelineScreen.kt#AddEditMaintenanceRecordSheet }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/MaintenanceTimelineViewModel.kt#MaintenanceTimelineViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/MaintenanceSuggestionsViewModel.kt#MaintenanceSuggestionsViewModel }
  - { kind: doc, role: intent, target: README.md }
---

# Log maintenance

Adds a maintenance record to a vehicle's timeline: a built-in task, an inspection that defers a replacement, or a custom entry, with an optional receipt. Offered from the timeline, from a suggestion's Log now, and from the Log Service quick action.
