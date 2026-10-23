# RoomScan for Android

A native Kotlin starter for room scanning with ARCore. The live camera view visualizes ARCore-detected planes; the scan summary records the number of tracked floor-like and wall-like surfaces as JSON in the app's private files directory.

## Current scope

- Android native app (Kotlin + ARCore, no Expo or React Native runtime).
- Detects horizontal and vertical planes and uses the Depth API when supported.
- Start/finish scan control and on-device JSON summary.
- Debug APK is built by GitHub Actions on every push and can also be started manually.

This is an early scanning foundation, not a complete room reconstruction or a dimensionally accurate floor plan. ARCore plane estimates vary by device, lighting, texture, and how the user scans. A later phase can add boundary capture, dimensions, persistence/export, and validation against real rooms.

## Try it

Use an ARCore-supported Android phone with Google Play Services for AR installed. Push a commit to GitHub, then open **Actions → Android debug APK → Artifacts** and download `roomscan-debug-apk`. Install the APK on the phone and grant camera access.

The app id is `com.apreez.roomscan`. Scan JSON files are saved inside app-private storage as `room-scan-<timestamp>.json` and are not uploaded anywhere.

## Build locally

Open this folder in Android Studio or run `./gradlew assembleDebug` (Windows: `gradlew.bat assembleDebug`). The output is `app/build/outputs/apk/debug/app-debug.apk`.

## Upstream attribution

The rendering/session foundation is adapted from Google's ARCore Hello AR Kotlin sample. See `LICENSE` for the upstream Apache 2.0 license.
