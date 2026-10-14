---
availability:
  - { place: garage-app }
domain: obd2-scanner
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdViewModel.kt#ObdViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/obd/ObdParser.kt#ObdParser }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/obd/ObdScanResult.kt#ObdScanSummary }
  - { kind: doc, role: intent, target: README.md }
---

# Scan vehicle

Connects to the vehicle through the saved OBD2 adapter and reads its health: battery voltage, check engine light and emissions readiness, stored, pending and permanent trouble codes with freeze frame, odometer and distance since codes were cleared, the VIN and a sensor snapshot. The scan is logged on the vehicle's timeline.
