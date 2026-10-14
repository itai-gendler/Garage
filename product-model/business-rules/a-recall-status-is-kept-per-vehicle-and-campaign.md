---
appliesTo:
  - { type: capability, id: change-recall-status }
  - { type: capability, id: check-recalls }
  - { type: entity, id: recall }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/RecallCampaignState.kt#RecallCampaignState }
---

# A recall's status is kept per vehicle and campaign, and every campaign starts Open

A status survives NHTSA being unreachable and is shown again whenever the campaign is listed.
