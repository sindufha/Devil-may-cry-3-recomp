# Adaptive icon and application-name fix

[Back to overview](../README.md)

The combined v0.28 release includes the fix for [issue #1](https://github.com/sindufha/Devil-may-cry-3-recomp/issues/1),
which reports an oval, cropped icon on the default POCO Launcher on Android 13
and suggests the shorter application name **DMC3**.

## Cause and change

The previous foreground layer contained only a centered 60 x 26 dp logo. The
background gradient had no intrinsic size. Android derives an adaptive icon's
intrinsic width and height from the maximum dimensions of its layers; therefore
the icon advertised a wide, rectangular intrinsic size instead of a square.
This explains the oval shape in the report, subject to device confirmation.

The foreground now includes a transparent 108 x 108 dp sizing layer. The
background also declares a 108 x 108 dp size and continues to fill the bounds.
The same unmodified logo remains centered at 60 x 26 dp, whose corners fit inside
the central 66 dp safe circle. Both `icon` and `roundIcon` use the same adaptive
resource. The manifest label is **DMC3**, and the current launcher footer shows v0.28.

References: [Android adaptive-icon guidance](https://developer.android.com/develop/ui/compose/system/icon_design_adaptive)
and [AOSP intrinsic-size implementation](https://android.googlesource.com/platform/prebuilts/fullsdk/sources/+/88c7ff1cd72d6305ec59f97aadc2198cc2dc3592/android-34/android/graphics/drawable/AdaptiveIconDrawable.java).

## Review material and checks

- [Source patch](patches/v0.26-icon-fix.patch), relative to the local source
  workspace. It documents this focused change; this repository remains a
  documentation and APK distribution, not a complete buildable source tree.
- [Current build metadata](build-info.json).
- APK compilation, signing, complete function catalog and package-content audits
  passed. The compiled package label and version were checked with aapt2.
- Both layers have square intrinsic dimensions. Logo geometry fits the safe
  circle, and its original bitmap bytes are preserved.
- The local icon-only v0.26 build reused the native runtime and all 850 cached
  guest objects. The combined v0.28 release also includes the separately
  documented [widescreen changes](WIDESCREEN.md).

The user authorized publication of the combined v0.28 APK. The agent has not
opened the app, read the phone screen, or confirmed the rendered POCO Launcher
icon. The original icon patch remains available for review; no separate v0.26
release APK is published.
