---
availability:
  - { place: garage-app }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/obd/ObdDevicePickerDialog.kt#ObdDevicePickerDialog }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/obd/ObdAdapterConfig.kt#ObdAdapterConfig }
---

# Select OBD2 adapter

Chooses the OBD2 adapter Garage connects to: a paired Bluetooth adapter, a Bluetooth LE adapter found by scanning, or a Wi-Fi adapter. It is offered in Settings and from the OBD2 Scanner.
