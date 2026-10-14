---
appliesTo:
  - { type: capability, id: log-fill-up }
  - { type: capability, id: edit-fill-up }
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/fuel/FuelScreen.kt#FuelScreen }
---

# A fill-up needs an odometer reading, a volume and a total cost above zero

Price per volume is worked out from the total cost and volume when the fill-up is saved.
