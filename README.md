# Nivora for Android

Nivora is an independent, unofficial Android client built from the open-source Telegram for Android codebase. It is not affiliated with or endorsed by Telegram.

The app keeps Telegram's core messaging protocol and features while adding a separate visual identity and a carefully scoped set of interface changes. The first implementation pass applies Nivora branding, an iOS-inspired light palette, and removes Premium/Business upsell entry points from Settings. This does **not** bypass Telegram server-side Premium restrictions or unlock paid account features.

## Project status

This repository is the source project. A working APK has not yet been built or device-tested. The project still needs Nivora's own Telegram API credentials and a matching Firebase configuration for background notifications. Its Android application ID is `com.nivora.chat`. A dedicated, persistent release-signing key is required before a distributable release is ready.

See:
- [Russian setup guide](docs/SETUP_RU.md)
- [Product scope and implementation status](docs/STATUS.md)
- [Security notes](docs/SECURITY.md)

## Build requirements

The upstream project currently documents Android Studio 2025.1.4, Android SDK 36, and Android NDK 27.2.12479018. Clone with submodules:

```bash
git clone --recursive https://github.com/exeteee/nivora-android.git
```

Provide `NIVORA_API_ID`, `NIVORA_API_HASH` and a Firebase `google-services.json` for package `com.nivora.chat` through GitHub Actions Secrets as described in [docs/SETUP_RU.md](docs/SETUP_RU.md). Do not commit personal credentials, Firebase configuration, or release-signing material. The Actions workflow builds a test Debug APK; it is not a signed public release.

## Upstream and license

Nivora is based on [Telegram for Android](https://github.com/TelegramOrg/Telegram-Android). The upstream source is licensed under GNU GPL v2. Nivora changes are published in this repository under the same license; see [LICENSE](LICENSE).

Telegram is a trademark of its respective owner. Nivora is an unofficial third-party client.
