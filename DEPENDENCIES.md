# Dependencies

The mod is not a self-contained binary. The main QMod supplies
`libvrm-qavatars.so` and the pre-existing `libOVRLipSync.so`.

| Runtime package | Required version | Installation |
| --- | --- | --- |
| beatsaber-hook | 6.4.2 | Manifest download URL |
| custom-types | 0.18.4 | Manifest download URL |
| assimp | 5.3.3 | Install the supplied Scotland2 QMod first |
| bsml | 0.4.55 | Manifest download URL |
| chatplex-sdk-bs | 6.4.5 | Manifest download URL |
| paper2_scotland2 | 4.8.0 | Manifest download URL |
| lapiz | 0.2.23 | Manifest download URL |

Scotland2 must already be installed as the game's loader. Some packages require
further dependencies through their own manifests, including SongCore/tinyxml2.
The installer must support dependency downloads and have internet access.
The manifest is authoritative; a failed upstream download needs a compatible
manually installed QMod, not an arbitrary version substitution.

## Assimp provenance

Original project: https://github.com/BSQ-VRM/Assimp-QPM
Original release: https://github.com/BSQ-VRM/Assimp-QPM/releases/tag/5.3.3

The supplied package retains the upstream ARM64 `libassimp.so` byte for byte;
this port corrects the QMod loader/install metadata for Scotland2. It is an
unofficial packaging adaptation, not a new Assimp build.

SHA-256 of `libassimp.so`:
`603b8573800c81344fa2289642c80bc1fdf81550ca6be681050a1ba8a4185d51`

The original upstream QMod lacks Scotland2 metadata and can trigger a
QuestLoader repatch prompt. Keep Scotland2 and use the supplied corrected QMod.
Automatic Assimp downloading can be enabled only after its own release asset
has been published and verified. The prepared local main QMod intentionally
requires this dependency to be installed first.

## Build-time inputs

See the pinned QPM files for bs-cordl 4008.0.0, Scotland2 0.1.7, fmt 11.0.2,
Sombrero 0.1.43, conditional-dependencies 0.3.0, rapidjson-macros 2.1.0,
Kaleb 0.1.9 and transitive header packages. They are not all separately
installable mods. License treatment is described in LICENSE_REPORT_EN.md.
