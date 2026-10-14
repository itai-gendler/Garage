---
availability:
  - { place: garage-app }
domain: recalls
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/recall/RecallsViewModel.kt#RecallsViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/RecallRepository.kt#RecallRepository }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/remote/RecallApi.kt#RecallApi }
  - { kind: doc, role: intent, target: README.md }
---

# Check recalls

The Recalls tab: NHTSA safety recall campaigns for the vehicle's model year, make and model, open ones first, each with what is wrong, the risk, the remedy and NHTSA's parking advice.
