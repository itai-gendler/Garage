---
entities:
  - entity: vehicle
    shows: [VIN, Year, Make, Model, Trim, Drivetrain, Fuel type, Purchased new, Initial mileage, Photos, Current mileage, Engine and drivetrain specs, Body specs, Weights and towing, Manufacturing, Oil, Ignition, Filters, Tires, Wipers]
  - entity: maintenance-record
    shows: [Date, Mileage, Category, Task, Description, Cost, Receipt, Inspected only, Remind in distance, Remind in months]
    collects: [Date, Mileage, Category, Task, Description, Cost, Receipt, Inspected only, Remind in distance, Remind in months]
  - entity: fill-up
    shows: [Date, Odometer, Volume, Total cost, Price per volume, Full tank]
    collects: [Date, Odometer, Volume, Total cost, Full tank]
  - entity: charging-session
    shows: [Date, Odometer, Energy added, Charger speed, Battery start, Battery end, Total cost, Vendor, Vendor type, Range at full charge]
    collects: [Date, Odometer, Energy added, Charger speed, Battery start, Battery end, Total cost, Vendor, Vendor type, Range at full charge]
  - entity: custom-rule
    shows: [Task name, Category, Distance interval, Month interval, Notes]
    collects: [Task name, Category, Distance interval, Month interval, Notes]
  - entity: ignored-task
    shows: [Task name]
  - entity: recall
    shows: [Campaign number, Component, Summary, Consequence, Remedy, Reported date, Park it, Park outside]
  - entity: modification
    shows: [Title, Category, Description, Installation date, Cost, Product link, Photos]
    collects: [Title, Category, Description, Installation date, Cost, Product link, Photos]
  - entity: registration
    shows: [License plate, State, Expiration, Renewal fee, Notes, Photo]
    collects: [License plate, State, Expiration, Renewal fee, Notes, Photo]
  - entity: state-inspection
    shows: [Expiration, Last inspected, Result, Notes]
    collects: [Expiration, Last inspected, Result, Notes]
  - entity: emissions-test
    shows: [Expiration, Last tested, Result, Notes]
    collects: [Expiration, Last tested, Result, Notes]
  - entity: inspection-sticker
    shows: [Expiration, Sticker number, Notes]
    collects: [Expiration, Sticker number, Notes]
  - entity: insurance-policy
    shows: [Provider, Policy number, Expiration, Premium, Agent contact, Notes, Photo]
    collects: [Provider, Policy number, Expiration, Premium, Agent contact, Notes, Photo]
  - entity: toll-pass
    shows: [Expiration, Account, Notes]
    collects: [Expiration, Account, Notes]
  - entity: settings
    shows: [Include mods in cost]
    collects: [Include mods in cost]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/vehicle/VehicleDetailScreen.kt#VehicleDetailScreen }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/vehicle/VehicleTab.kt#VehicleTab }
---

# Vehicle

One vehicle and everything kept about it: its timeline, maintenance schedule, fuel and charging log, expenses, specs, parts and fluids, mods, documents and recalls.

## Intent

Everything the Owner does for one vehicle happens without leaving it.
