---
appliesTo:
  - { type: capability, id: check-recalls }
  - { type: capability, id: generate-vehicle-service-book }
  - { type: entity, id: recall }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/RecallRepository.kt#RecallRepository }
---

# Recalls are matched by model year, make and model

NHTSA offers no recall lookup by VIN, so a listed campaign may not apply to the specific vehicle; the Owner can mark it as not affecting the vehicle, or check the VIN on NHTSA's site.
