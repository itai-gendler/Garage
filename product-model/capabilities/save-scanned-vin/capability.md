---
availability:
  - { place: garage-app }
domain: obd2-scanner
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdViewModel.kt#ObdViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/obd/ObdParser.kt#ObdParser }
---

# Save scanned VIN

Stores the VIN the car reports on a vehicle that has none.
