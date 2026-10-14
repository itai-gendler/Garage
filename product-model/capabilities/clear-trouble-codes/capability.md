---
availability:
  - { place: garage-app }
domain: obd2-scanner
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdViewModel.kt#ObdViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/obd/ObdParser.kt#ObdParser }
---

# Clear trouble codes

Asks the vehicle to clear its stored and pending trouble codes, which turns off the check engine light and resets readiness monitors, and logs the clearing on the timeline.
