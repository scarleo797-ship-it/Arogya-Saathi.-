# Arogya Saathi — Android prototype

A first prototype for an elderly-friendly, offline-first medicine reminder app.

## Included in this prototype
- Marathi, Hindi, and English interface strings.
- Local medicine list storage.
- Scheduled daily local notifications.
- Optional spoken feedback when the user marks a medicine as taken.
- Triple-tap SOS button that opens the SMS app with a prefilled message to a saved contact.
- Barcode scanning that reads a barcode value.

## Important limitations
- The barcode scanner does **not** yet connect to a verified medicine database. A scanned barcode alone does not identify the medicine's use or safety.
- SOS opens the SMS composer; it does not silently send a message or confirm delivery.
- SOS location sharing, caregiver alerts, robust missed-dose tracking, and production-grade reminder recovery are not implemented yet.
- The reminder scheduler currently uses Android's inexact-alarm mode. Notifications may be delayed by Android/device power settings. This prototype must be tested before anyone relies on it for medication.
- This is a development prototype, not a medically validated product.

## Build an APK using GitHub Actions (phone browser workflow)
1. Create/sign in to a GitHub account in your browser.
2. Create a **public or private repository** named `arogya-saathi`.
3. Extract this ZIP if your phone's file manager supports it.
4. Upload the extracted project files and folders to the repository. Do not upload only the ZIP file.
5. Ensure `.github/workflows/build-apk.yml` is included.
6. Open the repository's **Actions** tab and enable Actions if prompted.
7. Run the workflow named **Build Android APK**, or push a commit to start it.
8. When the workflow finishes successfully, open that workflow run, scroll to **Artifacts**, and download `arogya-saathi-apk`.
9. Extract the downloaded artifact ZIP to obtain `app-release.apk`.

If uploading nested folders from a phone browser is difficult, use GitHub's web editor to add the workflow and files, or ask someone with a computer to upload the project once.

## Build locally
Install Flutter and Android build tools, then run:
```bash
flutter pub get
flutter build apk --release
```
The APK should be produced at `build/app/outputs/flutter-apk/app-release.apk`.
