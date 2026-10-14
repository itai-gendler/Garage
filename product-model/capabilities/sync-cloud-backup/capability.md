---
availability:
  - { place: garage-app }
domain: data-and-privacy
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/WebDavBackupRepository.kt#WebDavBackupRepository }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/notification/CloudBackupWorker.kt#CloudBackupWorker }
---

# Sync cloud backup

Uploads garage-backup.zip to the Owner's WebDAV server, when the Owner taps Sync now and once a day on its own.
