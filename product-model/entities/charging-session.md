---
domain: fuel
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/ChargingRecord.kt#ChargingRecord }
---

# Charging session

One charge of an electric or plug-in hybrid vehicle.

## Information kept

- **Date** — when the vehicle was charged
- **Odometer** — the odometer reading at the charger
- **Energy added** — kWh added
- **Charger speed** — Level 1 (120V), Level 2 (240V) or DC Fast Charging
- **Battery start** — battery percentage before charging
- **Battery end** — battery percentage after charging
- **Total cost** — what the session cost, which may be nothing
- **Vendor** — where the vehicle was charged, such as a network's name
- **Vendor type** — Home or Public
- **Range at full charge** — the estimated range at 100% charge, used to track battery health
