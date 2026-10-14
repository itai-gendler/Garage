---
entities:
  - entity: drivers-license
    shows: [Number, Issuing state, Expiration, Notes, Front photo, Back photo]
    collects: [Number, Issuing state, Expiration, Notes, Front photo, Back photo]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/dashboard/DashboardScreen.kt#DashboardScreen }
---

# Driver's License

The Owner's driver's license: number, issuing state, expiration, notes and photos of both sides.
