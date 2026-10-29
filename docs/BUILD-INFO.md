# Build information

[Back to overview](../README.md)

| Field | Value |
| --- | --- |
| Preview version | v0.25 / `0.25-branded-preview` |
| Version code | 25 |
| Build date | October 29, 2026 |
| Package | `local.dmc3.runtimeprobe` |
| Architecture | ARM64 / `arm64-v8a` |
| APK | `DMC3-Android-arm64-v0.25.apk` |
| APK size | 53,470,524 bytes / 50.99 MiB |
| Package API minimum / target | 26 / 28 |
| Bundled driver loader minimum | API 28 / Android 9 |
| Development device | Poco F3, Android 13, Adreno 650, 6 GB RAM |
| Game catalog | 19,152 linked functions |
| Native runtime | Unchanged from v0.24 |
| Renderer | DXVK Native 2.6.2 |
| Bundled driver | v27.0.0-20261028-r4 |

This development-signed APK uses the same application ID and local signing
certificate as earlier previews, allowing an update to retain app data. The
private signing key is not distributed. The package API floor does not establish
Android 8 device compatibility.

## APK SHA-256

```text
9ef80afc5a66b18764e32c0a201a7fb82cb4f916a40b6c5c50324cbb96ee2861
```

## Native runtime SHA-256

```text
15ac11cc10cd5c68b5ea5e08a5b9a4f76cef1e59eb48a72cd3a466040b8fe41d
```

The native library and all 850 cached guest objects are reused. Only the Java
launcher, Android resources, branding notice and APK packaging changed for v0.25.
Build work uses command-line tools, one worker, two logical CPUs and below-normal
priority. No performance improvement is claimed from the branding change.

## Supported game EXE SHA-256

```text
49f80df5cce75d2a2b942f25c8ebe6ac6aceac87e7869c8e35073a96397cf8f4
```

The EXE is provided by the user and imported separately. The APK bundles no
EXE, AFS archive, gameplay texture/model, audio/movie asset or save data. Its
only game-branded bitmap is the explicitly added launcher/app-icon logo.
Documentation screenshots are not packaged.

Machine-readable details: [build-info.json](build-info.json).
Release-file fingerprints: [SHA256SUMS](SHA256SUMS).
Release: [v0.25 on GitHub](https://github.com/sindufha/Devil-may-cry-3-recomp/releases/tag/v0.25).
