---
entities:
  - entity: vehicle
    shows: [VIN, Year, Make, Model, Trim, Photos]
  - entity: maintenance-record
    shows: [Date, Mileage, Category, Description, Cost]
  - entity: modification
    shows: [Title, Cost]
  - entity: recall
    shows: [Campaign number, Component]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/maintenance/export/MaintenanceExportScreen.kt#MaintenanceExportScreen }
---

# Seller Report Generator

Where the Owner chooses what goes into the vehicle's service and history book and generates it as a PDF.
