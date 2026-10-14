---
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/MaintenanceRecord.kt#MaintenanceRecord }
---

# Maintenance record

One entry on a vehicle's timeline: a service the Owner logged, an odometer check-in, an OBD2 scan or the clearing of trouble codes.

## Information kept

- **Date** — when it happened
- **Mileage** — the odometer reading at the time
- **Category** — Tires, Brakes, Battery, Fluids, Inspection, Repair or Other
- **Task** — the maintenance task it fulfils, such as Brake fluid flush, Odometer Check-in or OBD2 Scan; none for an Other / custom entry
- **Description** — what was done, in the Owner's words or the scan's summary
- **Cost** — what it cost, in the chosen currency
- **Receipt** — an attached receipt or invoice image or PDF
- **Inspected only** — whether the part was inspected and its replacement deferred
- **Remind in distance** — for an inspection, how far to drive before the task is due again
- **Remind in months** — for an inspection, how many months until the task is due again
