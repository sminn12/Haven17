# Harvest Haven — Android Test APK (fixed workflow)

This repository packages the selected Harvest Haven HTML build in a Capacitor Android test app.

## GitHub upload / repair

Upload the *contents* of this folder to the root of your existing repository `Haven17`, replacing the existing `.github/workflows/android-test-apk.yml`, `package.json`, `capacitor.config.json`, and `www/index.html` when prompted. Make sure `.github/workflows/android-test-apk.yml` is preserved as a nested path. The corrected workflow generates the Android project with Capacitor and runs Gradle from the generated `android/` directory; it does not run Gradle from the repository root where `app/` does not exist.

If the GitHub upload interface does not let you replace nested files cleanly, open each existing file in GitHub, choose the pencil/edit option, replace its contents with the matching file from this package, and commit. For `www/index.html`, upload the supplied file to that exact path and choose to replace it.

## Build

1. Open the repository's **Actions** tab.
2. Select **Build Harvest Haven Android Test APK**.
3. Run workflow if the push did not trigger a run.
4. When successful, open the run and download the `harvest-haven-debug-apk` artifact.
5. Extract the ZIP; install `app-debug.apk` on your Android device.

## Important

- This is a debug/test APK, not a Play Store release.
- The game currently loads Three.js from jsDelivr, so it still requires internet access for that dependency. This is not the offline build yet.
- This workflow has been reviewed for correct project paths, but has not been run on GitHub in this environment.
