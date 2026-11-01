# VRM Qavatars 1.1.58 — Beat Saber 1.40.8 / Scotland2

An unofficial Quest port of [VRM Qavatars](https://github.com/BSQ-VRM/VRM-Qavatars),
created by [FutureMapper](https://github.com/Futuremappermydud).
Port publication account: [VovchikN](https://github.com/VovchikN).

## Features

- VRM 0.0 custom avatars, VRIK, spring-bone physics, mirror and configurable expressions.
- Replay integration and retained VMC/full-body tracking code; device validation varies by feature.
- Arm extension capped at **+30%**, independent hand release beyond reach and smooth return.
- Crouch-aware reach checks, calibration improvements and settings update smoothing.
- Bloom bleed-through fix and reduced shockwave impact. Minor shoe/foot shimmer remains possible.

## Install and configure

Requires **Beat Saber 1.40.8_7379**, **Scotland2**, and the declared dependencies.
Install the supplied **Assimp 5.3.3 Scotland2 QMod first**, then the main QMod.
Other dependency downloads use the manifest links when supported by the installer.
Do not use the legacy QuestLoader Assimp package or repatch to QuestLoader.

Place your own avatars in:
`/sdcard/ModData/com.beatgames.beatsaber/Mods/VRMQavatars/Avatars`.
Choose **Match Armspans**, stand upright with arms extended horizontally, then
Recalibrate. Read README for the port-specific instructions and
[the original documentation](https://bsq-vrm.github.io/documentation/) for options.

## Downloads

- `VRM-Qavatars-1.1.58-BS1.40.8.qmod` — installable main mod.
- `assimp-5.3.3-Scotland2-1.40.8.qmod` — upstream Assimp binary with corrected loader metadata.
- `VRM-Qavatars-1.1.58-BS1.40.8-full.zip` — source, both QMods, notices, tests, patch,
  build/validation logs and debug symbols. Do not install this ZIP as a QMod.

## Validation and limitations

Rebuilt from beta.5.8 source with release version 1.1.58. Host regressions and
static package/ELF checks are documented in `docs/VALIDATION.md` and the archive.
Compilation does not prove runtime correctness. Earlier versions received
owner testing on Quest 3; the final release binary still requires a device smoke test.
Some third-party licensing/provenance questions remain unresolved; consult
`docs/LICENSE_REPORT_EN.md`. The root MIT license does not cover all bundled components.

## Original project

- [Original developer](https://github.com/Futuremappermydud)
- [Original source](https://github.com/BSQ-VRM/VRM-Qavatars)
- [Initial Publish 1.0.0 for Beat Saber 1.28](https://github.com/BSQ-VRM/VRM-Qavatars/releases/tag/1.0.0)
- [Setup and option documentation](https://bsq-vrm.github.io/documentation/)

This release is not an official update from the original author.
