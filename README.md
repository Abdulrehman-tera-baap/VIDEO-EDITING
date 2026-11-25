# MAAN Video Editing App — Android APK Development

Native Android WebView shell containing the MAAN HTML/CSS/JavaScript editor. This repository is separate from the GitHub Pages web edition.

## Build APK with GitHub Actions
1. Create a GitHub repository for this folder and push the files to `main`.
2. Open **Actions** and run **Build MAAN Android APK** (it also runs on pushes and pull requests).
3. Open the completed workflow run and download the `maan-debug-apk` artifact.
4. Install the debug APK on a test Android device. Android may ask you to allow installs from that source.

The workflow uses Java 17, Android SDK and Gradle 8.9. It produces a debug APK for testing, not a Play Store release. A signed release requires your own signing keystore and GitHub Actions secrets.

## Configure Supabase login
Edit `app/src/main/assets/www/config.js` and add your Supabase project URL and anon/public key. Never add a service-role key. Password handling is delegated to Supabase Auth. Use Row Level Security for any user data.

## Owner
Abdul Rehman · +92 316 0444503

## Current functionality
- Android WebView wrapper and file picker
- Local video import and preview
- Trim selection and browser MediaRecorder WebM export
- Filters, playback speed, rotation and fit/fill
- Guest mode and optional Supabase email/password login

## Not yet implemented
Multi-track timeline, merging multiple clips, music mixing, vocal removal, AI effects, MP4/H.264 export, native 4K export and project cloud sync are not complete. Browser-based export is device-dependent and may be constrained by memory and codecs. Test on real devices before distribution.

## Local build
Install Android Studio/SDK and Gradle 8.9, then run `gradle assembleDebug` from the repository root. Output: `app/build/outputs/apk/debug/app-debug.apk`.
