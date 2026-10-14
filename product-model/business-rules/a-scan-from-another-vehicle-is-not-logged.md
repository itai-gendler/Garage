---
appliesTo:
  - { type: capability, id: scan-vehicle }
  - { type: capability, id: save-scan-anyway }
  - { type: capability, id: clear-trouble-codes }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdViewModel.kt#ObdViewModel }
---

# A scan whose VIN differs from the vehicle's is kept off its timeline unless the Owner saves it anyway

A vehicle with no VIN accepts the scan and is offered the VIN the car reported.
