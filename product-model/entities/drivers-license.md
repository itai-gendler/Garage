---
domain: drivers-license
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/dashboard/DashboardViewModel.kt#DriversLicenseState }
---

# Driver's license

The Owner's own driver's license, kept once for the whole garage.

## Information kept

- **Number** — the license number
- **Issuing state** — the state or jurisdiction that issued it
- **Expiration** — when it must be renewed
- **Notes** — class, endorsements and notes
- **Front photo** — a photo of the front
- **Back photo** — a photo of the back
