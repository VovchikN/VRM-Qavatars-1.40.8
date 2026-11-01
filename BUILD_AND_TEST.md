# Building and tests

Use the tool versions and Linux/WSL build command in README. The existing
PowerShell scripts are retained for developers, but the validated release
packaging path is `scripts/build-linux.sh` / `tools/package-qmod.py`.

For an external build directory:

```bash
qpm restore
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=RelWithDebInfo \
  -DCMAKE_TOOLCHAIN_FILE="$ANDROID_NDK_HOME/build/cmake/android.toolchain.cmake" \
  -DANDROID_ABI=arm64-v8a -DANDROID_PLATFORM=android-24
cmake --build build --parallel 4
qpm qmod manifest --offline
python3 tools/package-qmod.py
```

For exact accompanying Sombrero header sources, select them with
`tools/use-local-sombrero.py` after restore and before compiling.
The prebuilt Assimp and OVRLipSync libraries are not rebuilt by this command.
Game-generated interfaces are restored by QPM and are not included in the source ZIP.

Host regressions (host Clang/C++20 required):

```bash
c++ -std=c++20 -Iinclude tests/arm-reach-guard.cpp -o /tmp/arm-reach-guard
/tmp/arm-reach-guard
python3 tests/check-arm-reach-pose.py
python3 tests/check-spine-pose.py
python3 tests/check-avatar-load-order.py
python3 tests/check-avatar-rendering.py
```

For Clang-specific tests, set `CXX` to a host-capable clang++ executable.
These tests compile actual selected solver/material method bodies with host
math and Unity stubs. They do not execute Unity, IL2CPP, headset tracking,
real avatar skinning or game postprocessing. The historical bloom GPU test
uses Mesa/EGL and minimal shaders rather than Quest/MToon game rendering.

`tools/audit-build.py` checks exports, all strong symbol imports against the
restored dependencies and Android API24 libraries, retained subsystem symbols,
object count and embedded shader identity. It requires the historical beta.5.5
full archive as its baseline. `tools/package-qmod.py` verifies archive entries,
manifest loader/version, ELF class/architecture and absence of TEXTREL.

The packager defaults to the published Scotland2 Assimp asset URL. Its public
download was verified byte-for-byte before this default was added.
`--assimp-url` can explicitly select another verified release asset owned by
VovchikN. The incompatible upstream QuestLoader download is never used.
