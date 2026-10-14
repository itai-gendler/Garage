---
appliesTo:
  - { type: capability, id: import-backup }
  - { type: capability, id: export-backup }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/BackupRepository.kt#BackupRepository }
---

# Importing a backup replaces all records and photos, and a backup from a newer version of Garage is refused

The backup is checked before anything is touched; once restored, Garage must restart to load it.

## Rationale

An older Garage cannot open data saved by a newer one, and would no longer start.
