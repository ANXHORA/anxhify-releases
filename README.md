# ANXHIFY

**Your music, clipped on.**

Official releases for ANXHIFY - a music platform with a native Android app and a web player. This
repository holds the released builds; the source lives elsewhere.

---

## Download

Go to **[Releases - Latest](https://github.com/ANXHORA/anxhify-releases/releases/latest)** and pick
the build for your device.

| Build | File | For |
|---|---|---|
| Mobile | `ANXHIFY-<version>-MOBILE.apk` | Phones and tablets |
| Android TV | `ANXHIFY-<version>-TV.apk` | Android TV and Google TV |

For example, 3.2.6 is `ANXHIFY-3.2.6-MOBILE.apk` and `ANXHIFY-3.2.6-TV.apk`.

**Take the one that matches your device.** The two builds are the same application - same package,
same signing key, same version - but the TV build runs in television mode: it opens on a sign-in
screen you complete from a phone, uses blur instead of the liquid-glass shader, and starts in the
light theme. Installing the TV build on a phone, or the mobile build on a television, will install
successfully and then behave like the wrong device.

Both are published on the same release under a flavour suffix precisely so the in-app updater can
tell them apart. It selects its own file and refuses the other's.

| | |
|---|---|
| Package | `com.anxhora.anxhify` |
| Version | 3.2.6 (beta) |
| Requires | Android 8.0 (API 26) or newer / Android TV 8.0 or newer |
| Signing | APK Signature Scheme v2 |

### Install on a phone

1. Download the `-MOBILE` `.apk` on the device.
2. Open it. Android asks once for permission to install apps from this source - allow it. This is
   required for anything distributed outside the Play Store, and it is also what lets ANXHIFY
   install its own updates.
3. Tap **Install**.

Installing over an older ANXHIFY build keeps your library and settings.

### Install on a television

The television build is sideloaded - there is no Play Store listing for it.

1. Download the `-TV` `.apk` onto the television, or send it to the television with whatever tool
   you normally use to move files to it.
2. Open it and allow installation from that source when asked.
3. Tap **Install**.

Signing in is done from a phone: the television shows a QR code and a short code, and you approve
it at **id.anxhora.shop/mytv**. Once the television is installed it keeps itself up to date.

---

## Verify before installing

Every release lists its SHA-256 per artefact. Check the file you downloaded:

```bash
sha256sum ANXHIFY-3.2.6-MOBILE.apk
```

Compare against the value in that release's manifest. They must match exactly.

---

## Updates

Updates are delivered **inside the app**: Settings -> System update. One tap downloads the build
and hands it to the Android installer. No browser is involved at any point.

The updater reads this repository directly, so a build installed from here finds every future
release on its own. It picks the artefact matching the device it is running on - `-MOBILE` on a
phone, `-TV` on a television - so an update can never move you to the other build.

### One thing worth knowing

Android only allows an in-place update when the new build is signed with the **same key** as the
installed one. ANXHIFY's current releases use:

```
SHA-256  17A94774FB1AC915723A3DC69E87F6245A4408AB6553BD63D612AD4E70B31994
```

Builds **before 3.0.0** were signed with a different key. An app installed from one of those
cannot be updated in place - Android refuses with `INSTALL_FAILED_UPDATE_INCOMPATIBLE`, and no
in-app action can work around it. The fix is a single uninstall, then install the current build
fresh.

---

## Previous versions

Older releases remain visible so the version history - and each release's notes - can be read.
They are **not** recommended for installation: each release supersedes the last, and the latest is
the only build that is kept current.

Installing the current build over any 3.x install keeps your data.

If you are on a build from before 3.0.0, uninstall it once and install the current build fresh -
see the signing note above.

---

## Links

| | |
|---|---|
| Web player | [web.anxhify.anxhora.shop](https://web.anxhify.anxhora.shop) |
| Download page | [web.anxhify.anxhora.shop/download](https://web.anxhify.anxhora.shop/download) |
| TV sign-in | [id.anxhora.shop/mytv](https://id.anxhora.shop/mytv) |
| Deep-link host | `anxhify.anxhora.shop` |

Shared song links look like `https://anxhify.anxhora.shop/song/<id>`. On a device with the app
installed the link opens the app; otherwise it opens the web player.

---

## Reporting a problem

Open an [issue](https://github.com/ANXHORA/anxhify-releases/issues) and include:

- the version (Settings -> About)
- your Android version, and whether it is a phone or a television
- what you did, what you expected, and what happened

For playback problems, the app keeps its own log - **Settings -> Advanced -> Playback logs**.
Including those lines turns "playback is broken" into a specific, fixable fault, because they
record which stream client was tried and what the server answered.

---

## License

The ANXHIFY Android app is distributed under the **GNU General Public License v3.0**.

It is derived from [Convx](https://github.com/cosmictaserdev-creator/Convx) 1.5.2, also GPL-3.0.
Upstream attribution and the full license text are retained with the source, as the license
requires.
