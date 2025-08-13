# Flutter Picsum BLoC App

Two screens:
- **Login**: Email & Password validation using BLoC.
- **Home**: Fetches 10 images from `https://picsum.photos/v2/list?limit=10` and shows them in a vertical list with proportional padding. Each cell has the image (full width, dynamic height based on aspect ratio), Title (Montserrat Semi-Bold), and Description (Montserrat Regular, max 2 lines).

## Tech
- Flutter (Dart)
- BLoC (`flutter_bloc` + `equatable`)
- HTTP (`http`)
- Fonts via `google_fonts` (Montserrat)

## Run
1. Ensure Flutter SDK is installed.
2. Create a new project (optional) or use this as-is inside a Flutter project root.
   ```bash
   flutter pub get
   flutter run
   ```
3. **Android Internet Permission**: In your project `android/app/src/main/AndroidManifest.xml`, add:
   ```xml
   <uses-permission android:name="android.permission.INTERNET"/>
   ```
   (Place it **outside** the `<application>` tag.)

## Build APK
```bash
flutter build apk --release
```
The APK will be at `build/app/outputs/flutter-apk/app-release.apk`.

## Notes
- Login uses local validation rules. If email/password pass validation, tapping **Login** navigates to Home (this fulfills navigation + BLoC validation). API integration is used on Home screen (Picsum).
