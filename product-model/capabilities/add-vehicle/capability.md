---
availability:
  - { place: garage-app }
domain: my-vehicles
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/vehicle/AddEditVehicleViewModel.kt#AddEditVehicleViewModel }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/VehicleRepository.kt#VehicleRepository }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/remote/VinDecoderApi.kt#VinDecoderApi }
  - { kind: doc, role: intent, target: README.md }
---

# Add vehicle

Adds a vehicle to the garage, typed in by hand or filled in by decoding its VIN with NHTSA, typed or scanned from its barcode.
