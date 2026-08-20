# OpenCode Mobile Build Instructions

This document outlines how to bump the app version and build OpenCode Mobile for iOS and Android.

## 1. Version Bumping

Before generating a new release, update the version number in these two files:

1. **`app.config.ts`**: Update `expo.version` (e.g., `"1.0.11"`).
2. **`package.json`**: Update the `"version"` field (e.g., `"1.0.11"`).

---

## 2. Building for iOS

iOS builds require a combination of Expo's native project generation and Xcode compilation/archiving:

1. **Prebuild / Generate Native Projects (if configuration changed):**
   ```bash
   npx expo prebuild --platform ios
   ```
2. **Run on local iOS simulator**  (Optional)
   ```bash
   npx expo run:ios
   ```
3. **Open in Xcode:**
   Open `ios/OpenCodeMobile.xcworkspace` directly in Xcode.
4. **Archive / Export:**
   - In Xcode, select **Product > Archive**.
   - It will encourage you to distribute the app in the UI
   - Alternatively, once archived, use the Xcode Organizer to export your IPA file (saving release artifacts under `RELEASES/`).

---

## 3. Building for Android

For Android release and development builds, use the provided npm scripts:

- **Android Release Build:**
  ```bash
  npm run build:android
  ```
- **Android Development Build:**
  ```bash
  npm run build:development:android
  ```
