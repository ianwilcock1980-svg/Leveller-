# Caravan Leveler

Android app for caravan levelling using the phone's built-in accelerometer.

## Features

- **Live pitch and roll** in degrees
- **Large visual spirit-level** display with colour feedback
- **Calibration** button for the phone's installed position
- **Caravan dimensions** for correction-distance estimates (front/rear/left/right in cm)
- **Host mode** – sensor phone streams data over local TCP
- **Remote mode** – second phone shows live readings from the sensor phone
- Local TCP on **port 45678** (no cloud, no internet required)
- Screen stays awake while the app is open

## Second-phone setup

1. Connect both phones to the same Wi-Fi network, **or** start a hotspot on one phone and connect the other to it.
2. Open **Caravan Leveler** on the phone placed inside the caravan.
3. Open the **Remote** section → **Start Host**.
4. Note the displayed host IP address.
5. On the second phone open the app → enter the host IP → **Connect Remote**.
6. The second phone now shows live pitch and roll from the sensor phone.

The sensor phone should stay in the same position after calibration. Use a solid, repeatable mounting point on the caravan floor.

## Requirements

- Android 8.0 (API 26) or higher
- Device with accelerometer
- Target SDK 35

## Build with Android Studio

1. Open the project in **Android Studio** (Hedgehog or newer recommended).
2. Let Android Studio download the Android Gradle Plugin and required Gradle distribution.
3. Click **Run** (green play button) or use **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
4. The debug APK will be at `app/build/outputs/apk/debug/app-debug.apk`.

## Automatic APK builds (GitHub Actions)

This project includes a workflow at `.github/workflows/build.yml`.

1. Push the project to a GitHub repository.
2. Open the repository’s **Actions** tab.
3. Select **Build Caravan Leveler APK**.
4. Choose **Run workflow**.
5. When finished, download **caravan-leveler-debug-apk** from Artifacts.

The workflow also runs automatically on pushes and pull requests to `main`.

To create a GitHub Release containing the APK, run the workflow manually and set **release** to `true`.

## Roadmap ideas (future Camping Assistant)

- Caravan and motorhome profiles
- Saved dimensions and multiple vehicles
- Voice instructions
- Wear OS display
- Hitch height memory
- Payload and nose-weight calculator
- Departure and arrival checklists
- Sun and satellite finder
- Restaurant finder
- Route and towing-rule information

## Tech stack

- Kotlin
- Jetpack Compose + Material 3
- Android SensorManager (accelerometer)
- Kotlin Coroutines + Flow
- Local TCP sockets (java.net)

## Licence

MIT – free to use, modify and distribute.
