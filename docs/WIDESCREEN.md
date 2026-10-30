# Widescreen and aspect-ratio settings

[Back to overview](../README.md)

The v0.28 APK combines the icon/name fix, widescreen patch, settings selector,
and the startup correction tested after the local v0.27 build.

## Settings

Open **MENU > Graphics > Aspect Ratio** and choose **Widescreen 16:9** or
**Original 4:3**. Widescreen is the default. The selected aspect and render size
are saved only when the renderer confirms a successful change. Both modes can
be selected again while the session is running.

| Preset | Widescreen 16:9 | Original 4:3 |
| --- | --- | --- |
| 1 | 854 x 480 | 640 x 480 |
| 2 | 960 x 540 | 800 x 600 |
| 3 | 1024 x 576 | 960 x 720 |
| 4 | 1152 x 648 | 1024 x 768 |
| 5 | 1280 x 720 | 1280 x 960 |
| 6 | 1440 x 810 | 1440 x 1080 |
| 7 | 1600 x 900 | 1600 x 1200 |

854 x 480 is a rounded 16:9 size. The mode preserves 16:9 on wider phone
screens, so side margins can remain. This setting does not stretch the picture
to the phone's full aspect ratio.

## Implementation and review

The patch extends the original resolution validator, corrects the camera's
horizontal and vertical calculations, and adjusts HUD, text, and combo-indicator
scaling. Settings use the existing guest window-message/resource-rebuild path;
the renderer acknowledges the actual backbuffer dimensions before persistence.

The local v0.27 regression wrote a scale factor to protected game-image data
at 0x7491DC and stopped during startup. v0.28 removes that write and scales
the loaded constant at instruction 0x6DD801 in both lifted entries instead.
The original data remains read-only and unchanged.

- [Focused source patch](patches/v0.28-widescreen.patch), applied after the
  [icon/name patch](patches/v0.26-icon-fix.patch) to the local source workspace.
  These review patches do not make this documentation repository a complete
  reproducible source distribution.
- [Build details](BUILD-INFO.md) and [validation/status](STATUS.md).
- Address and formula reference:
  [ThirteenAG's archived DMC3SE widescreen fix](https://github.com/ThirteenAG/WidescreenFixesPack/blob/7f09e7433c141d5dfd69ab72503471c3e8b7212e/source/DevilMayCry3.WidescreenFix/dllmain.cpp).
  The Android implementation uses lifted-source transformations rather than
  bundling or loading the x86 ASI mod.

Twelve optimized function sources change within six guest batch objects;
844 other guest objects are reused. DXVK and GPU driver libraries are unchanged.
Original EXE/assets and baseline lifted sources are preserved.

## Validation and limits

Local ARM64 execution covers 19 patched-validator cases, six camera cases,
and six HUD-load cases with the constant page protected read-only. All pass,
including unchanged constant bytes and guest stack/register preservation.
Window/mailbox checks cover a transition to 16:9 and a return to 4:3. Java
graphics-option checks cover both sets of presets.

The user reached gameplay and reported low FPS during the first-boss encounter
on v0.28. A short presentation sample averaged approximately 15.5 FPS at
1280 x 720 on Poco F3. That performance problem remains unresolved. The agent
has not controlled the game or visually verified every menu, cutscene, camera,
or HUD element. Full campaign and other-device compatibility remain unverified.
