# ANXHIFY 🎵

**Your music, clipped on.**

Official releases and documentation for ANXHIFY — a music platform with a native
Android app and a web player. This repository holds the released builds; the source
lives elsewhere.

---

## Download

Head to **[Releases → Latest](https://github.com/ANXHORA/anxhify-releases/releases/latest)**
and grab the `.apk`.

The in-app updater reads this repository directly, so a build installed from here will
find every future release on its own.

| | |
|---|---|
| Package | `com.anxhora.anxhify` |
| Requires | Android 8.0 (API 26) or newer |
| Size | ~42 MB (R8-minified) |
| Signing | APK Signature Scheme v2, RSA 4096 |

### Install

1. Download the `.apk` on the device.
2. Open it. Android will ask once for permission to install apps from this source —
   allow it. This is required for any app distributed outside the Play Store, and it is
   also what lets ANXHIFY install its own updates.
3. Tap **Install**.

Installing over an older ANXHIFY build keeps your library and settings.

### Verify before installing

Every release lists its SHA-256. Check the file you downloaded:

```bash
sha256sum ANXHIFY-v3.1.3.apk
```

Compare against the value in that release's notes. They must match exactly.

---

## Updates

Updates are delivered **inside the app**: Settings → System update. One tap downloads
the build and hands it to the Android installer.

### One thing worth knowing

Android only allows an in-place update when the new build is signed with the **same key**
as the installed one. ANXHIFY's current releases use:

```
SHA-256  17A94774FB1AC915723A3DC69E87F6245A4408AB6553BD63D612AD4E70B31994
```

Builds **before 3.0.0** were signed with a different key. An app installed from one of
those cannot be updated in place — Android refuses with
`INSTALL_FAILED_UPDATE_INCOMPATIBLE`, and no in-app action can work around it. The fix is
a single uninstall, then install the current build fresh.

That is why older builds stay downloadable below, rather than being deleted: a device
stuck on a mismatched key needs an APK it can actually install.

---

## Previous versions

Older builds are kept as archived releases for rollback and for devices that cannot
take an in-place update. Each carries its own SHA-256.

Newest first:

- [v3.1.2](https://github.com/ANXHORA/anxhify-releases/releases/tag/v3.1.2)
- [v3.1.1](https://github.com/ANXHORA/anxhify-releases/releases/tag/v3.1.1)

Older releases than these are no longer published. The download page at
**[web.anxhify.anxhora.shop/download](https://web.anxhify.anxhora.shop/download)** lists
the current build and the archive in one place.

---

## Links

| | |
|---|---|
| Web player | [web.anxhify.anxhora.shop](https://web.anxhify.anxhora.shop) |
| Download page | [web.anxhify.anxhora.shop/download](https://web.anxhify.anxhora.shop/download) |
| Deep-link host | `anxhify.anxhora.shop` |

Shared song links look like `https://anxhify.anxhora.shop/song/<id>`. On a device with
the app installed, the link opens the app. Otherwise it opens the web player.

---

## Reporting a problem

Open an [issue](https://github.com/ANXHORA/anxhify-releases/issues) and include:

- the version (Settings → About)
- your Android version
- what you did, what you expected, and what happened

For playback problems, the app keeps its own log — **Settings → Advanced → Playback
logs**. Including those lines turns "playback is broken" into a specific, fixable fault,
because they record which stream client was tried and what YouTube answered.

---

## Licence

The ANXHIFY Android app is distributed under the **GNU General Public License v3.0**.

It is derived from [Convx](https://github.com/cosmictaserdev-creator/Convx) 1.5.2, also
GPL-3.0. Upstream attribution and the full licence text are retained with the source, as
the licence requires.
