---
availability:
  - { place: garage-app }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/export/MaintenanceExportViewModel.kt#MaintenanceExportViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/export/MaintenanceExportScreen.kt#generatePdf }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/PdfExportNotifier.kt#PdfExportNotifier }
  - { kind: doc, role: intent, target: README.md }
---

# Generate vehicle service book

Produces the vehicle's service and history book as a PDF for resale, insurance or the Owner's records: the vehicle and its specs, total care investment, safety recall status, parts and fluids, mods, fuel and charging if chosen, and the full maintenance log.
