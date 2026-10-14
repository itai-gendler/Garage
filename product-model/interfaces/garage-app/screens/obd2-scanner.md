---
entities:
  - entity: settings
    shows: [OBD2 adapter]
    collects: [OBD2 adapter]
  - entity: vehicle
    shows: [VIN]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdScannerScreen.kt#ObdScannerScreen }
---

# OBD2 Scanner

The live connection to the vehicle's OBD2 port: vehicle health and emissions readiness, trouble codes with freeze frame, distance readings, the VIN the car reports, a sensor snapshot and live data.
