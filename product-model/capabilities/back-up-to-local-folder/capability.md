---
availability:
  - { place: garage-app }
domain: data-and-privacy
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/AutoBackupManager.kt#AutoBackupManager }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/BackupRepository.kt#BackupRepository }
---

# Back up to local folder

Writes garage-backup.zip to the chosen phone folder, on request or by itself after changes while auto-backup is on.
