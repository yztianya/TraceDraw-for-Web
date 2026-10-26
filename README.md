# TraceDraw for Web — Android WebView project

This project packages `https://igtoth.github.io/tracedraw/` in a fullscreen Android WebView. The project name, app label, namespace, application ID, and artifact name all use TraceDraw for Web. No CorelDRAW naming is used in this project.

## Features
- Immersive fullscreen hides status and navigation bars; system bars can temporarily reappear with system gestures.
- Resizable activity for foldable phones and tablet-sized inner screens.
- JavaScript and DOM storage enabled.
- External web links open in the browser; GitHub Pages pages stay in the app.
- Basic file chooser and HTTPS download support.
- No ad SDK, ad network, tracking SDK, or analytics code included.

## Build a debug APK on GitHub
1. Download and unzip this project.
2. Create a new empty GitHub repository.
3. Upload all files and folders from this project to the repository's `main` branch.
4. Open the repository's Actions tab and select **Build TraceDraw for Web APK**.
5. Click **Run workflow** if needed, then wait for the green check mark.
6. Open the completed workflow run, find Artifacts, and download `TraceDraw-for-Web-debug-apk`.
7. Extract the artifact ZIP; inside is `app-debug.apk`. Transfer it to Android and install it.

The workflow builds a debug APK for testing and personal installation, not a Play Store release package.

## Build locally
Requirements: JDK 17, Gradle 8.9, Android SDK Platform 35 and Build Tools.

Run:
```bash
gradle assembleDebug
```
APK output: `app/build/outputs/apk/debug/app-debug.apk`

## Limitations
- This is a WebView wrapper, not a native port of TraceDraw.
- The web app loads from the internet; it is not offline.
- JavaScript Blob downloads, advanced file operations, WebAssembly performance, keyboard shortcuts, and stylus behavior need testing on the target device.
- Ordinary HTTPS downloads use Android DownloadManager. Blob-based downloads may require additional bridge code.
- No ad SDK is included, but this cannot remove ads later added to the website itself.
