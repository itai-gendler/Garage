---
singleton: true
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/PreferencesManager.kt#PreferencesManager }
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/data/local/CloudBackupPreferencesManager.kt#CloudBackupPreferencesManager }
---

# Settings

The choices the Owner makes for the whole app, kept once on the phone.

## Information kept

- **Setup completed** — whether the first-run setup has been finished
- **Language** — the app language, or the phone's own language
- **Units** — Metric (km, L, L/100km) or Imperial (mi, gal, mpg); Metric until chosen
- **Currency** — the currency symbol shown with every amount; US Dollar until chosen
- **Theme** — light, dark or follow the system
- **Default vehicle** — the vehicle quick actions and widgets act on, or none chosen
- **Affiliate links** — whether optional affiliate links and the Support Store are shown
- **Maintenance mileage notice window** — how far ahead of a due mileage a task counts as upcoming; 500 miles until changed
- **Maintenance time notice window** — how far ahead of a due date a task counts as upcoming; 10 days until changed
- **Document renewal reminders** — whether expiring documents and the driver's license are reminded; on until turned off
- **Document expiration notice window** — how many days ahead of an expiration a reminder starts; 30 days until changed
- **Show fuel trend graph** — whether vehicle cards show the fuel trend sparkline; on until turned off
- **Show fleet overview** — whether My Vehicles starts with the fleet summary; off until turned on
- **Include mods in cost** — whether modifications count toward the total cost of ownership
- **OBD2 adapter** — the Bluetooth, Bluetooth LE or Wi-Fi adapter the scanner connects to, or none
- **WebDAV cloud sync** — whether the daily upload to a WebDAV server is on
- **WebDAV server URL** — the folder on the Owner's WebDAV server that receives the backup
- **WebDAV username** — the account used on that server
- **WebDAV password** — the password for that account, kept encrypted on the phone
- **Last cloud sync** — when the last upload succeeded
- **Last cloud sync error** — why the last upload failed, if it did
- **Local folder auto-backup** — whether a backup is written to a phone folder after changes
- **Backup folder** — the phone folder that receives garage-backup.zip
- **Last local backup** — when a backup was last written to that folder
- **Last local backup error** — why the last folder backup failed, if it did
