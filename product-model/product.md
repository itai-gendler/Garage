---
id: garage
summary: A private, offline-first Android app for keeping every vehicle's service history, maintenance schedule, fuel and charging log, documents and running costs in one place.
category: automotive
tags: [vehicle-maintenance, fuel-log, cost-of-ownership, android, offline-first]
authors:
  - { name: fearmikey, url: https://github.com/fearmikey }
license: MIT
languages: [en, fr, de, pl, es, it, pt, nl, ru, tr]
limitations:
  - Garage keeps everything on the phone; there are no accounts and no Garage server.
  - Vehicle details and safety recalls come from NHTSA's public services, and recalls are matched by model year, make and model.
  - Amounts are kept in the one currency the Owner chooses and are never converted.
  - Suggested service intervals are a general starter set, not a manufacturer's schedule.
  - Restoring a backup replaces everything in the garage.
references:
  - { kind: doc, role: intent, target: README.md }
---

# Garage

Garage is a vehicle management app for Android. Owners keep a profile for each
vehicle, filled in from its VIN, log services, fill-ups and charging sessions,
and get suggested service intervals with reminders for maintenance that is due
and documents about to expire. Costs roll up into a cost-of-ownership view, safety
recalls are checked against NHTSA, an OBD2 adapter can read the car's own
diagnostics, and the whole history can be exported as a service book PDF or
backed up.

## Intent

Garage is meant to be "a modern, privacy-focused, comprehensive vehicle management
application" in which owners "track maintenance schedules, monitor fuel efficiency,
analyze cost of ownership, check safety recalls, and maintain detailed service
records for all their vehicles in one centralized hub". It must remain fully
functional offline: all records stay on the device or move only through backups
the Owner sets up, and it carries no ads, analytics or tracking.
