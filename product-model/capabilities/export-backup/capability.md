---
availability:
  - { place: garage-app }
domain: data-and-privacy
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/BackupRepository.kt#BackupRepository }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/settings/SettingsViewModel.kt#SettingsViewModel }
---

# Export backup

Saves every vehicle, record, rule and photo in the garage to one zip file the Owner chooses where to keep.
