---
appliesTo:
  - { type: capability, id: view-cost-of-ownership }
  - { type: entity, id: modification }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/cost/CostOfOwnershipViewModel.kt#CostOfOwnershipViewModel }
---

# Total cost of ownership adds maintenance, fuel and charging, and mods only when included

Registration fees and insurance premiums are not part of it.
