# JARVIS Native Android Starter

Package: `com.prince.jarvis`  
Language: Kotlin  
UI: Jetpack Compose  
Minimum Android: API 26  
Build: GitHub Actions / Gradle / JDK 17

## Included and implemented

- Native Android Compose application (not a WebView)
- Dark futuristic JARVIS home screen and animated-ready orb placeholder
- Text chat using Gemini `generateContent` API
- Editable API key and model ID settings
- Android SpeechRecognizer microphone input (runtime permission)
- Android TextToSpeech reply playback
- Basic chat history during the current app session
- Error messages for API/network failures
- GitHub Actions workflow that builds and uploads a debug APK

## Important limitations

This is a buildable starter, not the complete advanced JARVIS specification. The following are NOT implemented yet:

- Gemini Live bidirectional real-time voice/WebSocket session
- Verified Aoede voice integration
- Local “Hey JARVIS” wake-word engine or background microphone service
- AccessibilityService phone automation
- Multi-agent tool execution and post-action verification
- Persistent Room memory
- Floating orb service, boot startup, routines, CameraX/OCR
- Release signing, Play Store compliance audit, and full automated test suite

Do not treat a successful APK build as proof that these missing features work. Add and test them in separate phases before everyday or production use.

## Build with GitHub Actions using a phone

1. Create a new GitHub repository.
2. Upload the complete contents of this ZIP to the repository root (not the ZIP file itself).
3. Commit and push to the `main` branch.
4. Open the repository's **Actions** tab.
5. Open **Build JARVIS Android APK** and wait for the workflow to finish.
6. Download the `JARVIS-universal-debug-apk` artifact from the successful run.
7. Extract the artifact ZIP to get `JARVIS-universal-debug.apk`.
8. Install it on your Android phone. You may need to allow installation from your chosen file manager/browser.

## Configure Gemini

1. Open JARVIS.
2. Open Settings.
3. Enter your Gemini API key.
4. Confirm that the model ID is available to your API account.
5. Save settings and try a text prompt.
6. If the API returns an error, read the message and verify model availability, key permissions, quota, and network.

## Build requirements

- JDK 17
- Android SDK platform 35 and build tools 35.0.0
- Gradle compatible with the Android Gradle Plugin in `build.gradle.kts`

The GitHub Actions runner installs the required SDK components. If the build fails due to dependency or plugin availability, inspect the workflow log and update the project deliberately; do not mark the build as successful without a green workflow run.

## Security note

The API key is saved in app-private SharedPreferences in this starter, but this is not equivalent to a hardened production credential architecture. Do not publish a build containing your personal API key. Never commit the key to GitHub.
