---
domain: schedule
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/CustomMaintenanceRule.kt#CustomMaintenanceRule }
---

# Custom rule

A maintenance interval the Owner sets for one vehicle, beside or instead of the built-in tasks.

## Information kept

- **Task name** — the task to remind about
- **Category** — Tires, Brakes, Battery, Fluids, Inspection, Repair or Other
- **Distance interval** — every how far the task is due
- **Month interval** — every how many months the task is due
- **Notes** — the Owner's or the preset's note
