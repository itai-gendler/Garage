---
entities:
  - entity: vehicle
    shows: [Oil, Ignition, Filters, Tires, Wipers]
    collects: [Oil, Ignition, Filters, Tires, Wipers]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/vehicle/EditPartsScreen.kt#EditPartsScreen }
---

# Edit Parts & Fluids

Where the Owner fills in the vehicle's parts and fluids cheat sheet, optionally starting from Garage's estimates.
