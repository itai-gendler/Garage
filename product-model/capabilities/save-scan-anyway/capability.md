---
availability:
  - { place: garage-app }
domain: obd2-scanner
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdViewModel.kt#ObdViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/obd/ObdParser.kt#ObdParser }
---

# Save scan anyway

Logs a scan that was held back because the car reported a different VIN.
