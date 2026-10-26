# Pixel Photos Evolved

Backup and Video Boost controls for Google Photos, in Google Photos itself: **profile picture → Pixel Photos Evolved**. No launcher icon and no separate settings app. The page uses Photos' own fonts, colours, switches and motion.

<p>
<img src="https://raw.githubusercontent.com/MrxSiN/PixelPhotosEvolved/main/docs/screenshots/profile-menu.png" width="250">
<img src="https://raw.githubusercontent.com/MrxSiN/PixelPhotosEvolved/main/docs/screenshots/settings.png" width="250">
<img src="https://raw.githubusercontent.com/MrxSiN/PixelPhotosEvolved/main/docs/screenshots/diagnostics.png" width="250">
</p>

> [!IMPORTANT]
> Google decides backup eligibility and how storage is counted, on its servers. This module changes what Google Photos on this phone reports. It cannot promise unlimited storage, and using it may conflict with Google's terms of service. Check your account storage after enabling any backup option.

## Features

### Backup

| Setting | What it does |
|---|---|
| **Unlimited Original Quality** | Applies a Pixel XL (2016) identity inside Google Photos, so Photos offers the Pixel XL backup terms. Your phone's own editing features stay available. |
| **Unlimited Storage Saver** | Applies the identity of a selected older Pixel (Pixel 2 to Pixel 5a) instead. It and Unlimited Original Quality turn each other off. Photos only honours it with backup quality set to Storage saver. |

Identity changes apply when Google Photos starts: force-stop and reopen Photos after changing them.

### Video Boost

| Setting | What it does |
|---|---|
| **Video Boost** | Detects Video Boost recordings and uploads them with the phone's real identity, so Google can process them while other backups keep the backup identity. Only on phones that record Video Boost: Pixel 8 Pro and the Pixel 9–11 Pro series, including XL and Fold models. |
| **Latest video** | The last Video Boost state Photos reported. |

Videos processed with Video Boost count toward your Google Account storage, even when an unlimited backup option is on.

### Compatibility & diagnostics

Shows the module version, Android, device, Google Photos version, libxposed API and framework, and each feature as compatible, disabled or unavailable. Every hook is checked against the running Photos build before it is installed; a missing hook disables only its own feature. **Diagnostic logging** adds detail to `adb logcat -s PixelPhotosEvolved`.

## Scope

```text
com.google.android.apps.photos
```

## Requirements

- Android 17 (API 37), ARM64
- An Xposed framework with **libxposed API 102** (tested with Vector 2.2)
- Google Photos 7.97.0.1000520730

## Compatibility

| Android | Google Photos | Device | Status |
|---|---|---|---|
| 17 QPR1 (CP3A.261005.005) | 7.97.0.1000520730 | Pixel 8 Pro | ✅ Working |

## Installation

1. Install the APK from the release attached to this repository.
2. Enable **Pixel Photos Evolved** in your Xposed manager, scoped to **Google Photos**.
3. Force-stop Google Photos and open it again.
4. Profile picture → **Pixel Photos Evolved**.

## Source

[github.com/MrxSiN/PixelPhotosEvolved](https://github.com/MrxSiN/PixelPhotosEvolved). The module is canonical XAX; backup and Video Boost decisions run as a compiled Brainfuck policy (ARM64).

Not affiliated with or endorsed by Google. Google Photos and Pixel are trademarks of Google LLC.
