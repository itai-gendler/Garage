---
availability:
  - { place: garage-app }
domain: recalls
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/recall/RecallsViewModel.kt#RecallsViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/RecallStateRepository.kt#RecallStateRepository }
---

# Change recall status

Sets where a recall stands for the vehicle: Open, Serviced / Completed, or Does Not Affect Vehicle.
