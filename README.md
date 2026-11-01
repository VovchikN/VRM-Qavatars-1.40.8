# VRM Qavatars 1.1.58 — Quest / Beat Saber 1.40.8

An unofficial standalone Meta Quest port of **VRM Qavatars**, originally created by
[FutureMapper / Futuremappermydud](https://github.com/Futuremappermydud).
This port is maintained for publication by [VovchikN](https://github.com/VovchikN).
It is based on the latest beta.5.8 source, rebuilt with release version **1.1.58**.

- **Game:** Beat Saber **1.40.8_7379** (`com.beatgames.beatsaber`)
- **Platform:** standalone Meta Quest, Android ARM64
- **Mod loader:** **Scotland2**
- **Original project:** [BSQ-VRM/VRM-Qavatars](https://github.com/BSQ-VRM/VRM-Qavatars)
- **Original Beat Saber 1.28 release:** [Initial Publish 1.0.0](https://github.com/BSQ-VRM/VRM-Qavatars/releases/tag/1.0.0)
- **Avatar setup and option documentation:** [VRM Qavatars documentation](https://bsq-vrm.github.io/documentation/)

## Features

The port retains the original VRM 0.0 avatar importer, VRIK body solver,
spring-bone/hair physics, mirror, avatar settings, expression triggers,
automatic blinking, replay integration and VMC/full-body tracking code.
Availability in source does not mean every feature has been tested on this game version.

This version includes calibration/scale corrections, crouch following, material
initialization fixes, reduced bloom bleed-through, reduced shockwave distortion,
and smoother settings updates. Hands may stretch up to **30%** beyond their
calibrated arm length. Beyond **130%** they blend to a relaxed pose beside the
body; each hand reconnects independently within **125%**. The transition takes
approximately **0.20 seconds**. The check uses the current solved shoulder position,
including during crouching. This changes avatar IK only, leaving controller/saber
tracking and game hit detection under the game's control.

## Installation

1. Use Beat Saber **1.40.8_7379**, already patched with **Scotland2**. Back up your
   current mod installation/settings before upgrading. QuestPatcher is an installer;
   it is not the mod loader.
2. The final manifest includes a download URL for the compatible **Assimp 5.3.3
   Scotland2** package. A compatible online installer can download missing
   dependencies automatically. If downloading fails, manually install the supplied
   **`assimp-5.3.3-Scotland2-1.40.8.qmod`** first. The original upstream Assimp QMod
   has legacy QuestLoader metadata; do not repatch the game to QuestLoader.
3. Install **`VRM-Qavatars-1.1.58-BS1.40.8.qmod`** using QuestPatcher or another
   Scotland2-compatible QMod installer. Keep an internet connection available for
   the dependency URLs declared in the manifest. See [dependencies](DEPENDENCIES.md).
4. Copy your own `.vrm` files into:

   ```text
   /sdcard/ModData/com.beatgames.beatsaber/Mods/VRMQavatars/Avatars
   ```

5. Launch the game, open **VRM Qavatars**, refresh/select an avatar and calibrate.
   Use the [original setup guide](https://bsq-vrm.github.io/documentation/) for the
   full option reference. The guide also describes the original game version;
   installation and compatibility details above take precedence for this port.

No avatar models, songs or Beat Saber game files are included.

## Calibration

Select **Match Armspans** when fitting avatar scale to your reach. Stand upright,
hold both arms horizontally apart and keep that pose during the Recalibrate
countdown. Calibration applies according to the selected type; Fixed mode keeps
manual scale. Fit Height is a separate optional operation. The status text shows
measured head height, model measurements and applied scale.

Calibrate before judging the 30% arm stretch limiter. A badly scaled avatar can
reach that limit during ordinary motions.

## Testing and known limitations

Earlier builds were tested by the owner on a Quest 3. The owner reported that
Match Armspans corrected fitting, crouching became usable, and the bloom fix
removed the observed light bleed-through. These are user observations, not a
complete compatibility certification. **The final 1.1.58 binary has not been run
on a physical Quest by the builder.** See [validation](VALIDATION.md).

- A small amount of beat-synchronized distortion/shimmer can remain around shoes
  or feet. The GraphicsTweaks shockwave toggle did not fully remove it in the
  owner's setup. Complete elimination is not claimed.
- Genuine transparent materials can still have sorting/postprocess limitations.
- Replay/third-person behavior depends on the installed replay mod and its camera.
  The owner used third-person replays; other combinations remain untested.
- VMC, external full-body trackers, all expression options and all avatar rigs need
  device testing. VRM 1.0 material generation remains incomplete upstream.
- Experimental microphone lip-sync components are not attached by default.
- Dependency links require upstream assets to remain available.

## Source distribution

Complete sources are provided in **[VRM-Qavatars-1.1.58-Source.zip](VRM-Qavatars-1.1.58-Source.zip)** and in the full release archive. Extract the source ZIP before building. The repository root contains the publication documentation; GitHub's automatically generated repository archives are not the standalone build tree.

## Build

Use Android NDK **r27c / 27.2.12479018**, QPM **1.5.12**, CMake and Ninja.
The release was built for `arm64-v8a`, Android API **24**, using CMake 4.4.4 and
Ninja 1.13.2. Dependency versions are pinned in `qpm.json` and `qpm.shared.json`.

```bash
export ANDROID_NDK_HOME=/absolute/path/to/android-ndk-r27c
export QPM_BIN=/absolute/path/to/qpm
export BUILD_JOBS=4
bash scripts/build-linux.sh
```

The script restores dependencies, builds a new library, generates the manifest
and packages a QMod with notices. It does not install or run Beat Saber.
For rebuilding with the accompanying LGPL Sombrero sources, run
`python3 tools/use-local-sombrero.py` after `qpm restore`, then configure/build.
A non-symlink directory at that path must first be moved aside by the developer.
See [build and host tests](BUILD_AND_TEST.md).

## Credits and licenses

The original MIT copyright notice is preserved. The root license applies to the
mod authors' own code; it does not relicense dependencies or SDK binaries.
See [third-party notices](THIRD_PARTY_NOTICES.txt), [license report](LICENSE_REPORT_EN.md)
and the full texts in the `licenses/` directory of the source archive. Some component license/provenance
questions remain open and are listed explicitly; this package is not represented
as fully cleared for redistribution.

Thanks to the original developers and dependency authors:

- [Futuremappermydud](https://github.com/Futuremappermydud) — original VRM Qavatars.
- [Misticenea](https://github.com/Misticenea/VRM-Qavatars-1.40.8) — existing 1.40.8 port sources.
- [Gay-Axolotl](https://github.com/Gay-Axolotl/QavatarsRevived) — additional reference project.
- [zoller27osu](https://github.com/zoller27osu), [Sc2ad](https://github.com/Sc2ad),
  [jakibaki](https://github.com/jakibaki) — beatsaber-hook.
- [HardCPP](https://github.com/hardcpp) — ChatPlex SDK.
- [RedBrumbler](https://github.com/RedBrumbler), [FrozenAlex](https://github.com/FrozenAlex)
  and the contributors acknowledged by the original project.
- [Lauriethefish](https://github.com/Lauriethefish), [danrouse](https://github.com/danrouse),
  [BobbyShmurner](https://github.com/BobbyShmurner) — Quest mod template.

Please report port-specific bugs to the port repository, including the game/mod
versions, replay mod, avatar format and a relevant log excerpt. Remove personal
information from logs before posting. Original developers do not maintain or
endorse this unofficial release merely because they are credited here.
