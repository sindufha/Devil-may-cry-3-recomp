# Project status and validation

[Back to overview](../README.md)

This is a playable development preview, not a completed port or a certification
of the full game. The current build is v0.25, with the same native runtime as v0.24.

## Evidence from the user's device

The supplied screenshots are from the user's Poco F3 / Android 13 / Adreno 650.
They show the Special Edition title screen, Dante office gameplay and combat,
the original pause menu, and the Mission 2 briefing. They do not show a completed
campaign or gameplay throughout Mission 2.

The gameplay images display readings of 25.9 and 29.9 FPS. Title, pause, and
briefing captures display approximately 58–62 FPS. These are single captures
with unknown measurement conditions, not an average, benchmark, or fixed target.
Scene complexity, resolution, driver behavior, shader work, and temperature can
change performance. No new performance gain is claimed for the branding build.

## Implemented paths

| Area | Implementation / evidence |
| --- | --- |
| Game code | 19,152 catalog functions present in the linked ARM64 runtime |
| Rendering | DXVK Native 2.6.2; Android WSI, live resolution, and presenter reuse |
| GPU selection | Bundled Turnip or system driver; Poco F3 is the development hardware |
| Audio | DirectSound/Vox compatibility with AAudio music/effects mixing |
| Input | Xbox-style touch controller and custom layout editor |
| Save management | Separate normal/unlocked profiles, imports, history, and selection |
| Android lifecycle | Retained live process, surface reconnection, paused audio/timers |
| Back navigation | App-owned exit confirmation; native Back does not become game input |
| Branding | Special Edition logo in the adaptive app icon and launcher |

The source catalog count establishes code coverage at link time. It does not
establish that every execution path, mission, asset, or Windows API variant works.

## Local regression evidence

These checks run locally without controlling the phone:

- **118,552** layout checks across different viewports, insets and sizes, including
  edge drags, full-shape bounds, saved layouts, draft cancellation, and moved input.
- **601** touch-model checks and **305** DirectInput ABI checks.
- **278** native Back/touchscreen-mouse checks and **31** Java confirmation checks.
- **376** save-profile/FPS checks and **41** graphics-option checks.
- **725** lifecycle coordinator checks with cooperatively scheduled ARM64 contexts;
  **723** callback/renderer/audio method checks with controlled platform APIs.
- **156** Android WSI checks, including repeated replacement of the same window pointer.
- **66** window/live-resolution checks and **12** original resolution-validator cases.
- **17,275** checks of the patched presenter methods against controlled GPU/OS behavior.
- Package audits covering code-only runtime data, JNI contracts, driver provenance,
  source fingerprints, and the unchanged 850 cached guest objects.

Controlled API fixtures do not replace real GPU, Android thread scheduling,
audio-device behavior, or touch testing. The latest Back, editor, lifecycle and
branding work has not been end-to-end device-tested by the development agent;
the user performs physical testing.

## Unverified or incomplete

- Complete campaign progression and long sessions.
- Every mission, boss, character, difficulty, and progression-dependent mode.
- Movie/cutscene coverage and all asset/codec combinations.
- Devices other than the development Poco F3, including Mali and other Adreno generations.
- A fixed frame rate or a comprehensive thermal/battery profile.
- Restoring an unsaved session after process death, force stop, or task removal.
- General compatibility with other EXE revisions, mods, or HD Collection data.

Completed-save import enables a separate profile; it is not evidence that every
unlocked mode has been played through. Driver/API feature requirements remain
checked rather than bypassed or spoofed.
