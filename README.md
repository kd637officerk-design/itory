# Prime One for Windows

A Windows desktop wrapper for the Prime One music-player web interface extracted from the supplied `app-debug.apk`.

## What this repository contains

- The app's bundled web interface (`assets/index.html`).
- The bundled image assets (`assets/app-media/` and `assets/app-icon.png`).
- An Electron desktop shell configured for Windows 10/11 (64-bit).
- A GitHub Actions workflow that builds a Windows installer (`.exe`).

## Run on Windows

1. Install **Node.js 20 LTS** from https://nodejs.org/.
2. Extract or clone this repository.
3. Open PowerShell in the project folder.
4. Run:

   ```powershell
   npm install
   npm start
   ```

## Build the Windows installer

Run:

```powershell
npm install
npm run dist
```

The installer will be written to `dist/`. It is a 64-bit NSIS installer and can be installed on Windows 10/11.

## Build using GitHub Actions

1. Create a GitHub repository and upload these project files.
2. Push the repository to GitHub.
3. Open **Actions** and run **Build Windows installer**, or push a tag such as `v1.0.0`.
4. Download the `Prime-One-Windows-Installer` artifact from the workflow run.

## Compatibility notes

This is a desktop packaging/port of the APK's bundled web interface, not a recompilation of its Android-native Kotlin layer. Browser-based features such as the interface, web audio, local storage and IndexedDB are available through Electron. Android-only capabilities and integrations (including Android folder/media permissions, native background playback, notification controls, and any Android-specific cloud/file bridge) may need Windows-specific implementation and have not been verified here. Google API features may also require their own OAuth configuration and authorized origins.

The original app bundle identifies itself as **Prime One - Android Music Player** and describes cloud music, folder browsing, ID3 editing, equalizer, and offline playback. Those features are included in the bundled interface, but their operation on Windows must be tested with the relevant accounts, devices and API credentials.

## Source and licensing

This package was assembled from the APK supplied by the user. Confirm that you own or have permission to redistribute the original app and its bundled assets before publishing this repository publicly. Electron and electron-builder are installed from npm when building.
