---
availability:
  - { place: garage-app }
domain: data-and-privacy
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/settings/SettingsViewModel.kt#SettingsViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/AutoBackupManager.kt#AutoBackupManager }
---

# Change local folder auto-backup settings

Turns automatic backups to a folder on the phone on or off and chooses the folder, so another app can sync it anywhere.
