---
availability:
  - { place: garage-app }
domain: obd2-scanner
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdViewModel.kt#ObdViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/obd/ObdParser.kt#ObdParser }
---

# Start live data

Streams live engine readings such as RPM, speed and coolant temperature from the vehicle.
