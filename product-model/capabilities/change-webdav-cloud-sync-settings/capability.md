---
availability:
  - { place: garage-app }
domain: data-and-privacy
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/settings/SettingsViewModel.kt#SettingsViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/CloudBackupScheduler.kt#CloudBackupScheduler }
---

# Change WebDAV cloud sync settings

Connects Garage to the Owner's own WebDAV server for a daily backup upload, or turns that upload off.
