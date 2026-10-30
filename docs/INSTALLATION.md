# Installation and updates

[Back to overview](../README.md)

You must own your own PC copy of Devil May Cry 3: Special Edition and provide
**`dmc3se.exe`** and its matching game data. Read the [disclaimer](DISCLAIMER.md).

## Device requirements

The current APK is **ARM64 only**. Development testing has used a Poco F3
(M2012K11AG), Android 13, Adreno 650, with 6 GB RAM and 128 GB device storage.
This is a reference device, not a validated minimum specification.

The APK declares Android API 26 as its package minimum. The bundled Turnip loader
requires Android 9 / API 28 or later; Android 8 has not been validated. The GPU
and selected driver must satisfy DXVK 2.6.2's Vulkan feature checks. Merely having
a Vulkan option in a device specification is not a compatibility guarantee.
Use Turnip on the supported Adreno development device. The System driver option
is available for comparison; other GPUs remain unvalidated.

Keep enough storage for the installed native libraries, your full PC game folder,
an imported EXE, shader caches, and saves. The launcher reads large game assets
in place through Android's file access framework rather than duplicating them.

## Supported PC executable

The launcher accepts one exact executable target, identified by SHA-256:

```text
49f80df5cce75d2a2b942f25c8ebe6ac6aceac87e7869c8e35073a96397cf8f4
```

Select `dmc3se.exe` from your own compatible PC installation. Different executable
revisions and the HD Collection executable are not interchangeable with this
target. A rejected EXE does not replace an already valid imported copy.
This project does not supply an executable or instructions to acquire game data.

## Game folder

Copy the complete matching PC game folder to an accessible location on your device:

```text
DMC3/
├── dmc3se.exe
├── GDATA.AFS
└── native/
    ├── rom/
    └── sound/
```

Keep the original contents of those directories, including the native audio
files. The tree illustrates the required structure, not an exhaustive asset list.

## First launch

1. Install the APK and open **DMC3**.
2. Tap **Choose game EXE**, then select the matching executable. The launcher
   copies and verifies the EXE in its private storage.
3. Tap **Choose game folder**, select the folder above, and grant folder access.
   Assets stay in that folder and are opened read-only.
4. Keep the default Turnip selection on the Poco F3. Enable **Show FPS** if wanted.
5. Leave **Unlock All** off to use the normal progress profile, or import your
   own completed save as described below.
6. Tap **Start game**. Folder and EXE choices are retained for subsequent launches.

## Completed saves and save history

**Unlock All** selects a separate completed-save profile. It requires a compatible
completed PC `save0.sav`; a completed save is not embedded in the APK. Use
**Import completed save**, or allow the launcher to look for `save0.sav` in the
selected game folder. Normal progress is stored separately.

Use **Select save** to choose normal/unlocked progress, saved history entries,
or the completed template. Saving from the original game creates the active
profile's save and an archived entry. The template remains a separate choice.
Character and difficulty availability follow the selected save and game rules.

## Updating

Install a newer APK over the existing installation. Updates must use the same
application ID and signing certificate. This development build uses
`local.dmc3.runtimeprobe`; keep its data when updating.

Uninstalling or clearing app data removes private saves, history, the imported
EXE, folder permissions, and control preferences. Source game assets in the
external folder are not deleted by an ordinary update. Back up progress before
an intentional uninstall.

## Runtime settings

Open **MENU → Graphics** for live render resolution and FPS. Resolution changes
apply after releasing the slider. The presets retain the original 4:3 aspect:
640×480, 800×600, 960×720, 1024×768, 1280×960, 1440×1080, and 1600×1200.

These are render sizes, not the phone's physical display resolution. Lowering
resolution reduces GPU work, but does not remove CPU/runtime limits. Driver
selection is made in the launcher before starting a session.
