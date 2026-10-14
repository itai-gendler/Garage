---
entities:
  - entity: settings
    shows: [Language, Units, Currency, Theme, Default vehicle, OBD2 adapter, Document renewal reminders, Document expiration notice window, Maintenance mileage notice window, Maintenance time notice window, Show fuel trend graph, Show fleet overview, WebDAV cloud sync, WebDAV server URL, WebDAV username, Last cloud sync, Last cloud sync error, Local folder auto-backup, Backup folder, Last local backup, Last local backup error, Affiliate links]
    collects: [Language, Units, Currency, Theme, Default vehicle, OBD2 adapter, Document renewal reminders, Document expiration notice window, Maintenance mileage notice window, Maintenance time notice window, Show fuel trend graph, Show fleet overview, WebDAV cloud sync, WebDAV server URL, WebDAV username, WebDAV password, Local folder auto-backup, Backup folder, Affiliate links]
  - entity: vehicle
    shows: [Year, Make, Model]
references:
  - { kind: code, role: implementation, target: app/src/main/java/com/fearmikey/garage/ui/settings/SettingsScreen.kt#SettingsScreen }
---

# Settings

The app's settings: user preferences, reminders and expirations, integrations, data and privacy, and information about the app.
