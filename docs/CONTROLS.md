# Touch controls

[Back to overview](../README.md)

The overlay presents an Xbox-style controller. The original game still defines
the actions assigned to those inputs; changing the overlay position does not
change the controller binding.

| Control | Input |
| --- | --- |
| Left / right stick | Independent movement and camera axes |
| D-pad | Eight directions, including diagonals |
| A, B, X, Y | Face buttons |
| LB / RB | Shoulder buttons |
| LT / RT | Independent trigger buttons |
| LS / RS | Stick-click buttons |
| START | Original game Start; opens its pause/menu interface |
| MENU | Android custom settings, Resume, and Exit to main menu |
| Settings gear | Opens the same custom menu; stays available when controls are hidden |

Touch input supports multiple fingers. A stick can be held while pressing face
buttons, shoulders, and triggers. Releasing one touch does not release another.

## Android Back

With no custom panel open, Android Back displays:

> Do you want to exit the game?

- **Yes:** close the session and return to the launcher.
- **No:** close the confirmation and continue the same session.

Back on the confirmation also cancels it. Back in the custom menu closes that
menu; Back in the layout editor discards its draft and returns to settings.
Android Back is consumed by the app rather than sent as a game keyboard input.
It is distinct from MENU, START, and the original game's own cancel binding.

## Custom interface

Open **MENU → Controls → Custom interface**.

1. Drag a control in the preview to move it.
2. Tap a control, or select it from the list, to edit its individual size.
3. Resize from **50% to 200%** with the slider, +/−, or a second-finger pinch
   while holding the selected control.
4. Choose **Save layout** to apply the draft, or **Cancel** to discard it.

All 16 controls can be edited, including the gear, both sticks, MENU and START.
The selection list can reach a control hidden beneath another one. Overlap is
allowed, while the complete visual shape is kept inside the safe screen area.
The editor accounts for button dimensions, outlines, stick knobs, and notch insets.

**Reset layout** resets draft positions and individual sizes. Press Save layout
to retain that reset. The overall size and opacity remain separate preferences.
Layouts are stored in normalized coordinates and clamped again when the usable
viewport changes. Editing stays paused and sends no gameplay button presses.

## Overlay preferences and FPS

In **Controls**, change visibility, overall size (80–125%), and opacity (25–85%).
In **Graphics**, enable **Show FPS** to display successful-present frame rate
at the top center. Default top-row controls reserve space below it. Explicit
custom positions remain under your control, including possible overlap with FPS.

## Aspect ratio and render size

Open **MENU > Graphics > Aspect Ratio** and choose **Widescreen 16:9** or
**Original 4:3**. Widescreen is the default; an original-aspect choice is retained
after it is successfully applied. Adjust the render-resolution slider within
the selected ratio. Changes run through the game's normal resource rebuild.

The 16:9 presets range from 854 x 480 to 1600 x 900. Wider phone screens retain
side margins to preserve 16:9. See [widescreen details](WIDESCREEN.md).

## Backgrounding

Home and Recent Apps pause rendering, audio progression, and the guest clock.
Returning reconnects a recreated display surface to the retained session.
A custom-menu/editor pause remains active after returning. If Android kills
the process, the unsaved live session cannot be recovered from RAM; use game saves.
