# Premika — Java + Kotlin + XML migration foundation

This is a migration foundation, not a completed full native rewrite.

## What's included
- Java `MainActivity`
- Kotlin migration module/object
- XML Activity layout and purple theme
- Original Premika HTML bundled as `app/src/main/assets/index.html`
- WebViewAssetLoader local asset loading, JavaScript and DOM storage enabled

## Why this is staged
The supplied Premika source is a large working web app with Supabase Auth/Google OAuth, Realtime, database RPCs, LiveKit voice, private chat, BFF, gifts, wallet and admin flows. Rewriting all of those directly into native Java/Kotlin requires porting and testing each feature against the existing Supabase schema and Edge Functions. This foundation keeps the current app available while native screens and services are migrated one by one. It does NOT claim that the web UI has already been converted into native Android widgets.

## Build
Open this folder in Android Studio. Use JDK 17 and Android Gradle Plugin-compatible Android Studio, then Sync and Build APK.

## Important next migration steps
1. Move Supabase authentication/session and Google OAuth to native Android auth flow with a verified redirect/deep-link configuration.
2. Port profile, friends, messages, rooms and BFF screens into XML layouts + Java/Kotlin view models/services.
3. Port LiveKit room lifecycle and microphone permissions.
4. Port gift/wallet/admin RPC flows and validate each database function.
5. Test session persistence, realtime subscriptions, audio, payments and logout on device.

Do not publish any Supabase service-role key in the app. The provided HTML uses a publishable client key; keep privileged operations on server-side functions/RPCs with proper authorization.
