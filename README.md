<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://ai.google.dev/static/site-assets/images/share-ais-513315318.png" />
</div>

# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

View your app in AI Studio: https://ai.studio/apps/058a4728-e4a6-4dea-9c03-9af74ff11393

## Run Locally

**Prerequisites:**  [Android Studio](https://developer.android.com/studio)


1. Open Android Studio
2. Select **Open** and choose the directory containing this project
3. Allow Android Studio to fix any incompatibilities as it imports the project.
4. Create a file named `.env` in the project directory and set `GEMINI_API_KEY` in that file to your Gemini API key (see `.env.example` for an example)
5. Remove this line from the app's `build.gradle.kts` file: `signingConfig = signingConfigs.getByName("debugConfig")`
6. Run the app on an emulator or physical device
7. If you have already published your app in AI Studio, please [request upload key reset](https://support.google.com/googleplay/android-developer/answer/9842756#zippy=%2Crequest-an-upload-key-reset) in Google Play Console.

## OTA updates for sideloaded APKs

The app checks `version.json` when the Updates screen opens. For a public GitHub repository, set this Gradle property before building:

```properties
OTA_MANIFEST_URL=https://raw.githubusercontent.com/FebriGusti/galeri-simple/main/version.json
```

The configured repository is `FebriGusti/galeri-simple`. Publish `version.json` on the `main` branch and attach the release APK as `Galeri_Simple.apk` to each GitHub Release. Increase `versionCode` in `app/build.gradle.kts` for every release and keep it in sync with `version.json`; sign every release with the same release keystore. Android still requires the user to approve APK installation. Existing installations must manually install the first OTA-enabled release once.
