---
appliesTo:
  - { type: capability, id: change-user-preferences-settings }
  - { type: capability, id: view-cost-of-ownership }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/util/AppCurrency.kt#AppCurrency }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/MaintenanceRecord.kt#MaintenanceRecord }
---

# Changing the currency relabels amounts without converting them

Amounts are plain numbers in whatever currency the Owner uses; the currency setting only chooses the symbol shown.
