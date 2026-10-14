---
scope: The Garage Android app — vehicles, timeline, schedule and reminders, fuel and charging, expenses, specs, parts, mods, documents, recalls, driver's license, service book export, OBD2 scanner, widgets and shortcuts, settings, setup and backups.
method: Static inspection of source, resources and documentation at the pinned commit; nothing was run.
covered:
  - description: Room entities, data access and the database that keep vehicles and their records.
    paths: [app/src/main/java/com/fearmikey/garage/data/local/entity/, app/src/main/java/com/fearmikey/garage/data/local/dao/, app/src/main/java/com/fearmikey/garage/data/local/GarageDatabase.kt, app/src/main/java/com/fearmikey/garage/data/local/Converters.kt]
  - description: Preference stores for settings, the driver's license, the OBD2 adapter and backup destinations.
    paths: [app/src/main/java/com/fearmikey/garage/data/local/PreferencesManager.kt, app/src/main/java/com/fearmikey/garage/data/local/CloudBackupPreferencesManager.kt, app/src/main/java/com/fearmikey/garage/data/repository/PreferencesRepository.kt]
  - description: Repositories for vehicles, records, recalls, images and backups.
    paths: [app/src/main/java/com/fearmikey/garage/data/repository/]
  - description: Maintenance schedule engine, built-in intervals, presets and document expiration.
    paths: [app/src/main/java/com/fearmikey/garage/data/schedule/]
  - description: Fuel economy, charging efficiency, battery health and trend calculations.
    paths: [app/src/main/java/com/fearmikey/garage/data/fuel/]
  - description: NHTSA VIN decoding and recall clients.
    paths: [app/src/main/java/com/fearmikey/garage/data/remote/RecallApi.kt, app/src/main/java/com/fearmikey/garage/data/remote/VinDecoderApi.kt, app/src/main/java/com/fearmikey/garage/data/remote/dto/]
  - description: Reminder, PDF export and cloud backup workers, schedulers and notifications.
    paths: [app/src/main/java/com/fearmikey/garage/notification/CloudBackupScheduler.kt, app/src/main/java/com/fearmikey/garage/notification/CloudBackupWorker.kt, app/src/main/java/com/fearmikey/garage/notification/PdfExportNotifier.kt, app/src/main/java/com/fearmikey/garage/notification/ReminderCheckWorker.kt, app/src/main/java/com/fearmikey/garage/notification/ReminderNotifier.kt, app/src/main/java/com/fearmikey/garage/notification/WorkScheduler.kt]
  - description: OBD2 adapter connections, protocol parsing, trouble code descriptions and scan summaries.
    paths: [app/src/main/java/com/fearmikey/garage/obd/, app/src/main/resources/obd/]
  - description: Home screen widgets, launcher shortcuts and Quick Settings tiles.
    paths: [app/src/main/java/com/fearmikey/garage/widget/, app/src/main/java/com/fearmikey/garage/service/]
  - description: App entry, deep-link handling and navigation.
    paths: [app/src/main/java/com/fearmikey/garage/MainActivity.kt, app/src/main/java/com/fearmikey/garage/MainViewModel.kt, app/src/main/java/com/fearmikey/garage/GarageApplication.kt, app/src/main/java/com/fearmikey/garage/ui/navigation/, app/src/main/AndroidManifest.xml]
  - description: Screens and view models for setup, My Vehicles, the driver's license, vehicles and their tabs, expenses, recalls, mods, fuel, the service book export and the OBD2 scanner.
    paths: [app/src/main/java/com/fearmikey/garage/ui/startup/, app/src/main/java/com/fearmikey/garage/ui/dashboard/, app/src/main/java/com/fearmikey/garage/ui/vehicle/, app/src/main/java/com/fearmikey/garage/ui/maintenance/, app/src/main/java/com/fearmikey/garage/ui/fuel/, app/src/main/java/com/fearmikey/garage/ui/cost/, app/src/main/java/com/fearmikey/garage/ui/recall/, app/src/main/java/com/fearmikey/garage/ui/mod/, app/src/main/java/com/fearmikey/garage/ui/obd/]
  - description: Settings screen and view model.
    paths: [app/src/main/java/com/fearmikey/garage/ui/settings/SettingsScreen.kt, app/src/main/java/com/fearmikey/garage/ui/settings/SettingsViewModel.kt]
  - description: Shared components that carry behavior, such as the odometer dialog, vehicle card and currency choice.
    paths: [app/src/main/java/com/fearmikey/garage/ui/components/UpdateOdometerDialog.kt, app/src/main/java/com/fearmikey/garage/ui/components/VehicleCard.kt, app/src/main/java/com/fearmikey/garage/ui/components/CurrencySelectionDialog.kt, app/src/main/java/com/fearmikey/garage/ui/components/TrendChart.kt, app/src/main/java/com/fearmikey/garage/ui/components/StatusChip.kt]
  - description: Units, currency, number and date formatting, and task-name localization.
    paths: [app/src/main/java/com/fearmikey/garage/ui/util/, app/src/main/java/com/fearmikey/garage/util/]
  - description: Interface strings in English and their translations, the supported locales and the widget and shortcut declarations.
    paths: [app/src/main/res/values/strings.xml, app/src/main/res/values-de/, app/src/main/res/values-es/, app/src/main/res/values-fr/, app/src/main/res/values-it/, app/src/main/res/values-nl/, app/src/main/res/values-pl/, app/src/main/res/values-pt/, app/src/main/res/values-ru/, app/src/main/res/values-tr/, app/src/main/res/xml/]
exclusions:
  - description: Theme, colors, typography, icons, brand emblems and presentational components.
    paths: [app/src/main/res/drawable/, app/src/main/res/layout/, app/src/main/res/mipmap-anydpi/, app/src/main/res/mipmap-hdpi/, app/src/main/res/mipmap-mdpi/, app/src/main/res/mipmap-xhdpi/, app/src/main/res/mipmap-xxhdpi/, app/src/main/res/mipmap-xxxhdpi/, app/src/main/res/values-night/, app/src/main/res/values/colors.xml, app/src/main/res/values/themes.xml, app/src/main/java/com/fearmikey/garage/ui/theme/, app/src/main/java/com/fearmikey/garage/ui/components/Scrollbar.kt, app/src/main/java/com/fearmikey/garage/ui/components/SectionHeader.kt, app/src/main/java/com/fearmikey/garage/ui/components/EmptyState.kt, app/src/main/java/com/fearmikey/garage/ui/components/BrandEmblem.kt]
  - description: Dependency injection wiring and build configuration.
    paths: [app/src/main/java/com/fearmikey/garage/di/, app/src/main/java/com/fearmikey/garage/config/, app/build.gradle.kts, build.gradle.kts, settings.gradle.kts, gradle/, gradle.properties, app/src/main/keepRules/]
  - description: Generated database schema snapshots.
    paths: [app/schemas/]
  - description: Store listing, distribution metadata, CI and IDE files.
    paths: [fastlane/, fdroid/, .idea/, .github/]
  - description: Unit and instrumented tests, read as leads only.
    paths: [app/src/test/, app/src/androidTest/]
unmapped:
  - description: Two-way sync of records with a self-hosted server, its credentials, duplicate resolver and pending-delete queue.
    paths: [app/src/main/java/com/fearmikey/garage/data/remote/lubelogger/, app/src/main/java/com/fearmikey/garage/notification/lubelogger/, app/src/main/java/com/fearmikey/garage/ui/settings/LubeLoggerConfigDialog.kt, app/src/main/java/com/fearmikey/garage/ui/settings/LubeLoggerDuplicatesScreen.kt, app/src/main/java/com/fearmikey/garage/ui/settings/LubeLoggerDuplicatesViewModel.kt, app/src/main/java/com/fearmikey/garage/ui/settings/LubeLoggerStatusItem.kt]
  - description: Support Store, affiliate links and the donation prompt.
    paths: [app/src/main/java/com/fearmikey/garage/ui/settings/DeveloperFavoritesScreen.kt, app/src/main/java/com/fearmikey/garage/ui/components/BuyMeACoffeeDialog.kt]
limitations: []
---

# Coverage
