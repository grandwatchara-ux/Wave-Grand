# WAVE ECU RACING — Android source

## Build APK with GitHub Actions (phone-friendly)

1. Create a GitHub repository (Public or Private).
2. Extract this ZIP on your phone. Upload the **contents of the `WaveEcuRacing` folder** to the repository root. The `.github` folder must also be uploaded.
3. Make sure the default branch is `main` (or `master`).
4. Open the repository's **Actions** tab. If GitHub asks, enable Actions for the repository.
5. Select **Build Wave ECU Racing APK** in the left panel and tap **Run workflow** → **Run workflow**. A push to `main` or `master` also starts a build.
6. Wait for the run to finish with a green check. Open that run, scroll to **Artifacts**, and download `WaveEcuRacing-debug-apk`.
7. Extract the downloaded artifact ZIP. The installable file is `app-debug.apk`. Open it on Android to install (allow installation from that file app if Android asks).

## Project contents
- Kotlin + Jetpack Compose Android app
- Dark/green Honda Wave 110i racing dashboard
- CSV import and RPM / AFR / TPS graph
- Session Data Log
- Local read-only MAP profile list and draft creation
- GitHub Actions workflow at `.github/workflows/android-apk.yml`

## Important hardware limitations
This version is a **read-only/demo app**. It does not connect to a physical ECU, provide actual live ECU telemetry, send tuning commands, write fuel/ignition tables, or change rev limits. The LIVE label is reserved; imported CSV data is historical, and the dashboard starts in DEMO DATA mode. MAP profiles are local draft labels, not ECU binary maps.

Do not connect this app to a motorcycle ECU or rely on demo values for riding decisions. Confirm the exact ECU part number, model year, connector and supported protocol before selecting any adapter or attempting hardware integration.

## Build configuration
- JDK: 17
- Gradle: 8.9 (installed by GitHub Actions)
- Android Gradle Plugin: 8.7.3
- Compile SDK / Build Tools: 35
- Debug APK output: `app/build/outputs/apk/debug/app-debug.apk`
