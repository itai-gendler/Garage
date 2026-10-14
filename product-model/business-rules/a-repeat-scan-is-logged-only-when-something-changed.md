---
appliesTo:
  - { type: capability, id: scan-vehicle }
  - { type: entity, id: maintenance-record }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdViewModel.kt#ObdViewModel }
---

# A scan is logged only when its findings changed or the odometer advanced

The comparison is with the vehicle's last logged scan.

## Rationale

Repeated rescans would otherwise fill the timeline with identical entries.
