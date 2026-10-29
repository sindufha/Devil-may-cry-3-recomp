# Troubleshooting

[Back to overview](../README.md)

## The executable is rejected

Check the SHA-256 in [Installation](INSTALLATION.md). The port targets that exact
PC executable. Renaming another EXE does not make it compatible. An HD Collection
executable or an unrelated regional/revised binary cannot substitute for it.

## The game folder is not accepted

Choose the directory containing `GDATA.AFS`, not the archive itself or `native`.
Keep `native/rom` and `native/sound` intact. Grant the folder permission in the
Android picker. If the directory was moved or access was revoked, choose it again.

## A session stops or the display is blank

Record the build version, device/Android/GPU, driver selection, chosen resolution,
and the exact last action. Retry with the known supported files and a lower
render resolution. Driver features are verified; the runtime does not advertise
missing Vulkan capabilities to force startup. Other GPUs remain unvalidated.

If only the title/pause screen renders but a particular mission fails, report
the mission and active save profile. Reaching the main menu is not proof that
the affected gameplay path is complete.

## Performance is lower than the menu FPS

Compare gameplay to gameplay. The screenshots show higher readings in menus
than in the office combat scene. Lower the render resolution in MENU → Graphics
and compare the same scene. Rendering, lifted CPU work, driver state, shader
work, and device temperature can each limit the result.

## Music or effects are missing

Check that the complete matching `native/sound` folder is accessible and that
the app has valid folder permission. Include the scene and which sound category
is missing in a report. The APK intentionally contains no game audio.

## Vergil or a progression option is unavailable

Check the selected save. Unlock All requires your own compatible completed save
and uses a separate profile. The completed template remains in Select save;
normal progress is not overwritten by switching profiles. Availability is
controlled by the game/save, not by replacing the game with another edition.

## Controls are too small or overlap

Open MENU → Controls → Custom interface. Choose a control from the list, then
resize or drag it. This also selects a control covered by another one. Reset
layout resets the draft; Save layout commits it. The gear remains available
with gameplay controls hidden. Adjust FPS overlap through your custom positions.

## Back, Home, or Recent Apps behaves incorrectly

Android Back should show the exit confirmation when no custom panel is open.
No should continue the same session. Home/Recent Apps should retain a living
session and reconnect its surface on return. If the process was killed by the
system or removed, an unsaved session cannot be recovered; load an in-game save.

Report whether the confirmation appeared, whether audio continued, the elapsed
background time, and whether the launcher or the same scene appeared on return.

## Useful bug reports

Include the app version, device model, Android version, GPU/driver, resolution,
mission/character/save profile, and repeatable steps. A screenshot and a short
log captured immediately after the failure are useful. Avoid publishing game
archives, executable files, private signing keys, or unrelated personal data.

With USB debugging and ADB available, a local capture can be made with:

```sh
adb logcat -d -v threadtime > dmc3-logcat.txt
```

Review the capture before sharing it. Relevant runtime tags include
`DMC3RuntimeProbe`, `DMC3Launcher`, `DMC3D3D9`, `DMC3Audio`, and `DXVK`.
