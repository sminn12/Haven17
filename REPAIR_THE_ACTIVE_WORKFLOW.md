# Important: disable or replace the old workflow before rebuilding

The failed run still executes `gradle assembleDebug` from the repository root. That proves GitHub is running the old workflow, not the Capacitor workflow in this package.

1. In GitHub, open the repository's `.github/workflows/` directory.
2. Open the workflow file that contains the step `Run gradle assembleDebug --stacktrace`.
3. Replace that file's entire contents with the workflow in `.github/workflows/android-test-apk.yml`, OR delete/disable the old workflow.
4. Upload this package's `.github/workflows/android-test-apk.yml` at the exact path `.github/workflows/android-test-apk.yml`; keep `package.json`, `capacitor.config.json`, and `www/` at the repository root.
5. Commit the changes. If the old workflow remains enabled, it may continue running and failing even if the new workflow exists.
6. In Actions, confirm the new log runs `./gradlew assembleDebug` from the `android` directory. It must not run `gradle assembleDebug` from the repository root.

This workflow generates the Android project with Capacitor, checks that `android/app` exists, then builds and uploads the debug APK. This does not bundle Three.js offline; the game still uses its external CDN.
