# Build information

[Back to overview](../README.md)

| Field | Value |
| --- | --- |
| Preview version | v0.28 / `0.28-widescreen-startup-fix` |
| Version code / application name | 28 / DMC3 |
| Build date | October 30, 2026 |
| Package | `local.dmc3.runtimeprobe` |
| Architecture | ARM64 / `arm64-v8a` |
| APK | `DMC3-Android-arm64-v0.28.apk` |
| APK size | 53,491,004 bytes / 51.01 MiB |
| Package API minimum / target | 26 / 28 |
| Bundled driver loader minimum | API 28 / Android 9 |
| Development device | Poco F3, Android 13, Adreno 650, 6 GB RAM |
| Game catalog | 19,152 linked functions |
| Guest cache | 844 objects reused; six batch objects rebuilt |
| Renderer | DXVK Native 2.6.2 |
| Bundled driver | v27.0.0-20261028-r4 |
| Aspect ratios | Original 4:3 / Widescreen 16:9 |

The development signing certificate and application ID are retained, allowing
an in-place update without clearing data. The private signing key is not
distributed. The package API floor does not establish Android 8 compatibility.

## APK SHA-256

```text
c21fcc51d3d549b0e18b3b1e15a78730588ded19a25ce2bd3e94b4c5f7cced5f
```

## Native runtime SHA-256

```text
c959a44362b3ea3ecbaa4b14b4423bbc425d5f3c9b31264d3d53ea2bb6510ce5
```

The APK combines the square adaptive icon, DMC3 name, 16:9 camera/HUD patch,
aspect-ratio settings and the read-only HUD startup correction. Twelve targeted
lifted sources occupy six rebuilt guest batch objects. Original baseline lifted
sources, DXVK and GPU driver libraries are preserved. Build work uses one
worker, two logical CPUs and below-normal priority. No FPS improvement is claimed.

## Supported game EXE SHA-256

```text
49f80df5cce75d2a2b942f25c8ebe6ac6aceac87e7869c8e35073a96397cf8f4
```

Users must own the supported PC game and provide `dmc3se.exe` and the complete
matching game folder. The APK contains no original EXE, AFS archive, gameplay
texture/model, audio/movie asset or save data. The authorized branding logo is
its only game-branded bitmap; documentation screenshots are not packaged.

Machine-readable details: [build-info.json](build-info.json).
Fingerprint of the single release APK: [SHA256SUMS](SHA256SUMS).
Release: [v0.28 on GitHub](https://github.com/sindufha/Devil-may-cry-3-recomp/releases/tag/v0.28).
Licensing: [MIT](../LICENSE), [runtime/GPU notices](THIRD-PARTY-NOTICES.txt),
and [branding notice](BRANDING-NOTICE.txt).
