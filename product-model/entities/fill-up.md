---
domain: fuel
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/FuelRecord.kt#FuelRecord }
---

# Fuel fill-up

One visit to the pump for a vehicle.

## Information kept

- **Date** — when the tank was filled
- **Odometer** — the odometer reading at the pump
- **Volume** — how much fuel went in
- **Total cost** — what the fill-up cost
- **Price per volume** — total cost divided by volume, worked out when saved
- **Full tank** — whether the tank was filled to full; on unless the Owner turns it off
