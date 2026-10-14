---
domain: recalls
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/entity/RecallCampaignState.kt#RecallCampaignState }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/repository/RecallRepository.kt#VehicleRecall }
---

# Recall

An NHTSA safety recall campaign for a vehicle's model year, make and model. Garage keeps where each campaign stands for the vehicle; the campaign's own details come from NHTSA each time.

## Information kept

- **Campaign number** — NHTSA's campaign identifier
- **Component** — the affected component
- **Summary** — what is wrong
- **Consequence** — what can happen
- **Remedy** — what the manufacturer will do
- **Reported date** — when NHTSA received the report
- **Park it** — NHTSA advises not driving until repaired
- **Park outside** — NHTSA advises parking outside until repaired

## States

### Open

Not yet dealt with. Every campaign starts here.

### Serviced

The Owner has had the recall work done.

### Does not affect

The Owner has established the campaign does not apply to this vehicle.
