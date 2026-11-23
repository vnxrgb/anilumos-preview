# AniLumos Preview Builds

**Experimental downloads only.** This repository holds separately labelled AniLumos **Android mobile beta** and **Android TV / Amazon Fire TV alpha** packages.

- **Stable mobile releases:** https://github.com/vnxrgb/Anilumos/releases
- **Experimental packages:** https://github.com/vnxrgb/anilumos-preview/releases
- **Application source:** https://github.com/vnxrgb/Anilumos

## Which APK should I install?

| Label | Devices | Package type | Notes |
| --- | --- | --- | --- |
| `mobile-beta-signed-*` | Android phones and tablets | Release-signed `com.anilumos.app` | Experimental. Signed using the same release certificate as stable; Android version code must also permit upgrades. |
| `tv-alpha-signed-*` | Android TV / Amazon Fire TV | Debug-signed `com.anilumos.app.debug` | Experimental and remote/device testing still required. Signed with the release certificate; do **not** install on your phone. |

Each release is tied to a specific **source commit** and has a SHA-256 checksum, not a moving `latest` APK. Releases are marked **Pre-release** and cannot be mistaken for stable production releases. Source code, provider support, original package identifiers, and legal/attribution notices remain in the original project.

**Note:** the older release-signed mobile beta `v1.0.3-beta.1` remains at the [original release link](https://github.com/vnxrgb/Anilumos/releases/tag/v1.0.3-beta.1) until safely migrated. It is not the same as these debug previews.

### How to publish

Choose **Actions** in this repository and run **Publish mobile signed preview** or **Publish TV signed preview**. These workflows check out the corresponding source branches, run unit tests and lint, build the specific Android flavor, verify APK signing and packaging, and publish only on success.

**Publishing setup:** In this preview repository, open **Settings → Secrets and variables → Actions → Variables** and configure `ANILIST_CLIENT_ID`, `MAL_CLIENT_ID`, and `MAL_REDIRECT_URI` (using the same values as the source repository). The mobile workflow intentionally refuses to publish when these are missing. Set these **release-signing secrets** in this preview repository's Actions secrets: `ANDROID_SIGNING_KEYSTORE_BASE64`, `ANDROID_SIGNING_STORE_PASSWORD`, `ANDROID_SIGNING_KEY_PASSWORD`. Set the **Actions variables** `ANDROID_SIGNING_KEY_ALIAS` and `ANDROID_SIGNING_CERT_SHA256`. Use the exact same signing configuration as the original AniLumos release; the fingerprint check refuses mismatched certificates. Do not expose the keystore or passwords in commits or ordinary variables.

New signed previews use the pinned AniLumos release certificate and can upgrade matching-package installations when their version codes allow it. Experimental code can still have bugs; back up important app data before installing. Historical migrated debug APKs keep their original signing identity. Do not test real account credentials on untrusted devices.

## Attribution

AniLumos is based on AniLife: https://github.com/anilifecommunity/android-and-tv

This app uses code from Morphe. To learn more, visit https://morphe.software

See the source repository's LICENSE and attribution notices for applicable terms.
