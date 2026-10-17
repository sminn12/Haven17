# Harvest Haven — Android Test Project

This project packages the included Harvest Haven mobile prototype inside a lightweight Android WebView. It is a **test build**, not a Play Store release. The game currently runs as a local single-player prototype; it does not provide online accounts or multiplayer, and saves are local to this app installation.

## Important: repository folder layout

Upload the **contents** of `HarvestHavenAndroid` to the root of your GitHub repository. Do not upload only this ZIP, and do not put the project inside an extra nested folder. After upload, the repository root must show:

- `.github/workflows/build-apk.yml`
- `app/`
- `build.gradle`
- `gradle.properties`
- `settings.gradle`

The `app` folder contains the Android manifest, Java activity, styles, and `assets/index.html` game prototype. Keep the `.github` folder and its workflow file; they tell GitHub how to build the APK.

## Build the APK on GitHub

1. Open your repository on GitHub and confirm the files above are at the repository root.
2. Open **Actions**. If GitHub asks to enable workflows, enable them.
3. Choose **Build Harvest Haven APK** and tap **Run workflow**. If the workflow is not listed yet, make a commit/push to the `main` branch after uploading the files.
4. Open the latest workflow run and wait for the green check mark.
5. Scroll to **Artifacts** and download `Harvest-Haven-test-APK`.
6. Extract that downloaded artifact ZIP. It contains `app-debug.apk`.
7. Tap the APK to install it. Android may ask you to allow installation from your browser or file manager. Only install APKs you trust.

## If you are uploading from an Android phone

GitHub's mobile website can be awkward with folders beginning with a dot, such as `.github`. If the upload screen does not let you include `.github/workflows/build-apk.yml`, the build workflow will not appear in Actions. In that case, use GitHub's **Add file → Create new file** option to create the exact path `.github/workflows/build-apk.yml`, then paste the contents of that file from this project. Ensure the path is exact.

## Technical details

- Android application ID: `com.harvesthaven.app`
- Minimum Android version: Android 6.0 (API 23)
- Build: debug APK, built with Java 17, Gradle 8.9, Android Gradle Plugin 8.7.3
- Game content: local HTML/CSS/JavaScript inside Android WebView


## Walkable farm test
The current prototype includes a lightweight isometric farm scene with a touch joystick. Press and drag the on-screen joystick to move the farmer around the meadow. The center button returns the character to the middle; the sprout button displays an interaction hint. Keyboard arrow keys and WASD are also supported when running in a browser. This is a lightweight 2D-rendered isometric prototype, not a full 3D engine.
