# Changelog

[Back to overview](README.md)

## v0.26 - icon fix (pending confirmation)

- Keep both adaptive-icon layers square at 108 x 108 dp so the launcher does
  not derive an oval icon from the wide logo's intrinsic dimensions.
- Keep the complete logo centered inside the adaptive icon's safe area.
- Rename the installed application from DMC3 Android to DMC3.
- Reuse the v0.25 native runtime, GPU libraries, and all 850 cached guest objects.
- See the [issue #1 fix and validation](docs/ICON-FIX.md). Device appearance
  confirmation is pending; this candidate has not been published.

## v0.25 — branded preview

- Add the DMC3 Special Edition logo to the adaptive app icon and launcher.
- Add an English documentation set and six user-supplied Android screenshots.
- Keep the v0.24 native runtime unchanged; rebuild launcher/resources/APK only.
- Keep original game executables, gameplay assets, audio, movies, and saves out
  of the package. Only the explicit UI branding resource is added.

## v0.24 — Android Back

- Consume Android Back in both native and Java navigation paths.
- Show an English Yes/No exit confirmation; No resumes the current session.
- Prevent touchscreen navigation from becoming native mouse clicks while the
  Java touch controller is active.
- Preserve Back cancellation in settings/editor panels and real mouse/keyboard input.

## v0.23 — custom interface

- Add drag-to-position editing for all 16 controls, including MENU/START and the gear.
- Add individual 50–200% sizes, a size slider, +/−, and pinch resizing.
- Add Save layout, Cancel, and Reset layout with separate draft state.
- Clamp full control shapes to usable screen bounds and notch insets.

## v0.22 — background sessions

- Separate surface destruction from session cancellation.
- Park the game worker, release old presenters, and reconnect a new surface.
- Pause audio progression and the guest clock in the background.
- Preserve a custom-menu pause across background/foreground transitions.

## v0.19–v0.21 — runtime menu and navigation

- Add a Graphics/Controls session menu with live render-resolution requests.
- Keep START as direct game input and MENU as the custom-panel action.
- Correct Exit to main menu so the launcher does not automatically restart a session.
- Replace the top settings symbol with an eight-tooth gear.

## Earlier preview work

- Integrate DXVK 2.6.2 and Android presenter reuse for persistent SUBOPTIMAL results.
- Add Turnip loading, source/driver provenance checks, and a system-driver option.
- Implement touch input, original audio paths, save profiles/history and completed-save import.
- Link the complete 19,152-function catalog and reuse 850 optimized guest object units.

These entries summarize implemented changes. They do not claim complete campaign
testing or device verification of every feature; consult [Status](docs/STATUS.md).
