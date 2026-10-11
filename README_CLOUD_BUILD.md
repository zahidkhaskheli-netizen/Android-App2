# Build the APK online (no Android Studio)

This is a native Android/Gradle project. Use GitHub Actions to compile it in the cloud.

1. Sign in or create an account at https://github.com/.
2. Create a **private** repository (for example, `xauusd-signals`).
3. Upload the contents of this project folder to the repository root (the files `settings.gradle.kts`, `build.gradle.kts`, `app/`, and `.github/` must be at the repository root, not nested inside another folder).
4. Open the repository's **Actions** tab. If prompted, enable workflows.
5. Select **Build XAUUSD Signals APK** in the left sidebar and click **Run workflow**. Alternatively, pushing to the `main` branch triggers a build.
6. Wait for the workflow to finish successfully. Open the completed run, scroll to **Artifacts**, and download `xauusd-signals-debug-apk`.
7. Extract the downloaded artifact ZIP to get `app-debug.apk`. Transfer it to your Android phone, open it, and follow Android's installation prompts.

Notes:
- The workflow builds a **debug/test APK**, not a Play Store release.
- GitHub's cloud runner builds the app; Android Studio is not required on your laptop.
- Do not upload Exness passwords, API secrets, or account credentials to the repository.
- A successful build does not mean the live data provider is configured or the trading strategy is validated. Test the app and signals before relying on them.
