# Polarity — Android Studio build

This is a Capacitor project: your game (in `www/`) wrapped as a native
Android app. You'll need **Node.js** and **Android Studio** installed on
a computer (this can't be done from a phone).

## 1. Install dependencies
Open a terminal in this folder and run:
```
npm install
```

## 2. Add the Android platform
```
npx cap add android
```
This generates an `android/` folder — the actual native project.

## 3. Sync your web assets into it
```
npx cap sync android
```
(Re-run this any time you change files in `www/`.)

## 4. Open in Android Studio
```
npx cap open android
```
This launches Android Studio with the project loaded. Let it finish
Gradle sync (first time takes a few minutes — it downloads build tools).

## 5. Run or build
- **Test on a device/emulator:** click the green ▶ Run button.
- **Build a release APK:** `Build → Generate Signed Bundle / APK →
  APK`. Create a new keystore if you don't have one yet (Android Studio
  walks you through it) — save it somewhere safe, you'll need the same
  one for future updates. This produces a signed APK you can install
  or publish to the Play Store.

## Notes
- App ID is `com.polarity.game` and display name is `Polarity` — both
  editable in `capacitor.config.json` before step 2, or later in
  `android/app/build.gradle` / `strings.xml`.
- The app icon is set from `www/icon-512.png`. To customize Android's
  adaptive icon properly, right-click `android/app/src/main/res` in
  Android Studio → New → Image Asset.
- Everything in `www/` is the same game you've been testing in the
  browser — Capacitor just wraps it in a native WebView shell.
