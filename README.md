# AniLumos Preview Builds

**Experimental downloads only.** This repository holds separately labelled AniLumos **Android mobile beta** and **Android TV / Amazon Fire TV alpha** packages.

- **Stable mobile releases:** https://github.com/vnxrgb/Anilumos/releases
- **Experimental packages:** https://github.com/vnxrgb/anilumos-preview/releases
- **Application source:** https://github.com/vnxrgb/Anilumos

## Which APK should I install?

| Label | Devices | Package type | Notes |
| --- | --- | --- | --- |
| `mobile-preview-*` | Android phones and tablets | Debug-signed `com.anilumos.app.debug` | Experimental. Installs separately from the release-signed stable app; does not upgrade stable. |
| `tv-preview-*` | Android TV / Amazon Fire TV | Debug-signed `com.anilumos.app.debug` | Experimental and remote/device testing still required. Do **not** install on your phone. |

Each release is tied to a specific **source commit** and has a SHA-256 checksum, not a moving `latest` APK. Releases are marked **Pre-release** and cannot be mistaken for stable production releases. Source code, provider support, original package identifiers, and legal/attribution notices remain in the original project.

**Note:** the older release-signed mobile beta `v1.0.3-beta.1` remains at the [original release link](https://github.com/vnxrgb/Anilumos/releases/tag/v1.0.3-beta.1) until safely migrated. It is not the same as these debug previews.

### How to publish

Choose **Actions** in this repository and run **Publish mobile debug preview** or **Publish TV debug preview**. These workflows check out the corresponding source branches, run unit tests and lint, build the specific Android flavor, verify APK signing and packaging, and publish only on success.

**Mobile publishing setup:** In this preview repository, open **Settings → Secrets and variables → Actions → Variables** and configure `ANILIST_CLIENT_ID`, `MAL_CLIENT_ID`, and `MAL_REDIRECT_URI` (using the same values as the source repository). The mobile workflow intentionally refuses to publish when these are missing. Never enter sensitive passwords as variables.

These are *debug* APKs, not release-signed stable upgrades. Never use a preview APK to update an installed stable application. Do not test real account credentials on untrusted devices.

## Attribution

AniLumos is based on AniLife: https://github.com/anilifecommunity/android-and-tv

This app uses code from Morphe. To learn more, visit https://morphe.software

See the source repository's LICENSE and attribution notices for applicable terms.
