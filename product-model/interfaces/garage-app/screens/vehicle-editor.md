---
entities:
  - entity: vehicle
    shows: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos]
    collects: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/vehicle/AddEditVehicleScreen.kt#AddEditVehicleScreen }
---

# Vehicle editor

Where a vehicle is added or its details changed: VIN with decode and barcode scan, year, make, model, trim, drivetrain, fuel type, purchase condition, initial mileage and photos.
