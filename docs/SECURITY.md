# Nivora — безопасность и данные

Nivora is an unofficial third-party client based on the Telegram for Android source code. A complete security audit has not yet been performed. Do not describe this project as independently audited or more secure than Telegram.

## Credentials and build configuration

- Use an API ID and API hash issued for this Nivora application.
- Supply build values through Gradle properties, environment variables or GitHub Actions Secrets. Never commit personal credentials.
- The API ID/hash are embedded in the resulting client binary because the Telegram client protocol requires them; build-time secrets keep them out of the source repository but do not make them confidential after distribution.
- Use a Firebase project owned by the Nivora maintainer. The copied upstream Firebase JSON files were removed from the working branch.
- A Google Maps API key, when used, must be owned by the maintainer and restricted to the Android package `com.nivora.chat`.
- Never publish a release-keystore, private signing key, store password, Telegram login code, Telegram cloud password or recovery code.

## Telegram account restrictions

Removing Premium/Business promotional entry points is a user-interface change only. It must not bypass server-side feature checks, subscription requirements, rate limits, or access controls. Premium-only functions remain subject to Telegram's own account entitlements.

## Build and distribution

- Debug APKs are for testing only.
- A release build requires a dedicated long-term keystore that is not committed to Git.
- Keep the source changes public and comply with the upstream GPL-2.0 license.
- Verify the exact source revision and the build artifact before sharing an APK.
- Do not collect or upload private chats, contacts, session files, phone numbers or diagnostics from testers without their explicit consent.

## Scope of this note

This document records intended handling. It is not a security audit, penetration test, privacy certification, or guarantee against vulnerabilities in upstream code and dependencies.
