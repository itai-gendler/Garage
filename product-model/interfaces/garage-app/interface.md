---
type: mobile-app
actors: [owner]
entryPoints:
  - mobile-app: com.fearmikey.garage.action.LOG_FUEL
  - mobile-app: com.fearmikey.garage.action.UPDATE_ODOMETER
  - mobile-app: com.fearmikey.garage.action.LOG_SERVICE
references:
  - { kind: code, role: implementation, target: app/src/main/AndroidManifest.xml }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/MainActivity.kt#MainActivity }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/navigation/GarageNavHost.kt#GarageNavHost }
---

# Garage app

The Android app, with its home screen widgets, launcher shortcuts and Quick
Settings tiles. It works offline; it reaches out only to NHTSA, to an OBD2 adapter
and to the backup destinations the Owner sets up.

## Intent

One place on the phone for everything about the Owner's vehicles, usable with no
network and no account.
