# Third-party license and provenance report — 1.1.58

Prepared 2026-11-01. This report separates retained license texts from unresolved
provenance questions. It is not a blanket redistribution clearance or a claim of
infringement. Public availability of a download does not establish its license.

The original mod is MIT-licensed, copyright (c) 2023 Futuremappermydud. The
original LICENSE remains unchanged. VovchikN is credited for publication of this
unofficial port, not as the original mod author. No permission from or endorsement
by upstream developers is implied.

| Component | Version | License evidence | Scope / limitation | Source |
| --- | --- | --- | --- | --- |
| VRM Qavatars | original + 1.1.58 port | MIT | Original copyright preserved; does not cover third-party components. | [Upstream](https://github.com/BSQ-VRM/VRM-Qavatars) |
| beatsaber-hook | 6.4.2 | MIT | License from exact restored source retained. | [Upstream](https://github.com/QuestPackageManager/beatsaber-hook) |
| custom-types | 0.18.4 | MIT | License from exact restored source retained. | [Upstream](https://github.com/QuestPackageManager/Il2CppQuestTypePatching) |
| ChatPlex SDK | 6.4.5 | MIT; bundled dependencies have separate terms | SDK license retained; internal prebuilt component inventory is not fully attested. | [Upstream](https://github.com/hardcpp/QuestChatPlexSDK-BS) |
| Lapiz | 0.2.23 | MIT | Exact source license retained. | [Upstream](https://github.com/raineaeternal/Lapiz) |
| Scotland2 | 0.1.7 | MIT | Loader development dependency; not installed by this QMod. | [Upstream](https://github.com/sc2ad/scotland2) |
| Assimp QPM | 5.3.3 | BSD-3-Clause and internal dependency terms | Core notice retained; exact prebuilt internal inventory is incomplete. | [Upstream](https://github.com/BSQ-VRM/Assimp-QPM) |
| Sombrero | 0.1.43 | LGPL-2.1 | Exact restored header sources, license and rebuild selector included. | [Upstream](https://github.com/Fernthedev/sombrero-quest) |
| fmt | 11.0.2 | MIT | Exact version license retained. | [Upstream](https://github.com/fmtlib/fmt) |
| BSML | 0.4.55 | Unconfirmed for main component | No explicit main license identified in the earlier exact source audit. No MIT assumption. | [Upstream](https://github.com/bsq-ports/Quest-BSML) |
| Paper2 | 4.8.0 | Unconfirmed for main component | No explicit main license identified in the earlier exact source audit. | [Upstream](https://github.com/Fernthedev/paperlog) |
| Kaleb | 0.1.9 | Unconfirmed for main component | No explicit main license identified in the earlier exact source audit. | [Upstream](https://github.com/RedBrumbler/Kaleb) |
| RapidjsonMacros | 2.1.0 | Unconfirmed for wrapper | RapidJSON license does not establish the wrapper license. | [Upstream](https://github.com/Metalit/RapidjsonMacros) |
| conditional-dependencies | 0.3.0 | Unconfirmed for main component | Header package license not established by the earlier exact source audit. | [Upstream](https://github.com/QuestPackageManager/conditional-dependencies) |
| bs-cordl / libil2cpp | 4008.0.0 / 0.4.0 | Mixed / provenance review needed | Generated game interfaces and Unity SDK headers are not licensed by this project MIT notice. Restored through QPM, excluded from source ZIP. | [Upstream](https://github.com/QuestPackageManager) |
| OVRLipSync | header API 1.45.0; binary provenance unverified | Oculus/Meta SDK terms, not MIT | Header cites Oculus Audio SDK License 3.3; current published terms supersede older text. Applicable binary agreement/provenance not established. | [Upstream](https://developer.oculus.com/licenses/audio-3.3/) |
| UniVRM / MToon | retained shader bundle | MIT upstream; exact bundle provenance incomplete | Notices and shader patch tools included; upstream MIT alone does not prove provenance of every compiled bundle object. | [Upstream](https://github.com/vrm-c/UniVRM) |
| SongCore | 1.1.26 | MIT | Transitive runtime dependency; manifest/ELF/license checked in earlier audit. | [Upstream](https://github.com/raineaeternal/Quest-SongCore) |
| tinyxml2 | 10.0.0 | zlib | Transitive runtime dependency; retained license. | [Upstream](https://github.com/leethomason/tinyxml2) |
| utfcpp | restored with Paper2 | BSL-1.0 | Exact cached notice retained; upstream version not confirmed. | [Upstream](https://github.com/nemtrif/utfcpp) |
| RapidJSON | restored with beatsaber-hook | MIT and additional notices | Full retained license includes additional bundled notices. | [Upstream](https://github.com/Tencent/rapidjson) |
| nlohmann/json | 3.10.4 | MIT | Embedded header notice retained. | [Upstream](https://github.com/nlohmann/json) |
| VRM.h | version unspecified | MIT | Kota Iguchi 2021 notice retained. | [Upstream](https://github.com/BSQ-VRM/VRM-Qavatars) |
| kissnet | embedded, commit unspecified | MIT | Embedded header notice retained. | [Upstream](https://github.com/Ybalrid/kissnet) |
| OSCPP | embedded, commit unspecified | Permissive Stefan Kersten license | Exact notice retained. | [Upstream](https://github.com/kaoskorobase/oscpp) |
| And64InlineHook | from beatsaber-hook 6.4.2 | MIT | Rprop copyright/permission retained. | [Upstream](https://github.com/Rprop/And64InlineHook) |

## Other retained notices

The licenses directory also includes notices for EasyGifReader, cppcodec,
css-color-parser, curl, dyad, giflib, libwebp (including PATENTS), OpenSSL 1.1.1w,
openssl-curl-android wrapper, stb_image and Android NDK toolchain/sysroot material.
Their presence records known included or vendor-transitive material; it does not
prove that every such component is linked into the main mod. Paper2's Rust lock
file is not a verified compiled binary bill of materials. ChatPlex's internal
OpenSSL/curl/webp versions and full binary SBOM require supplier confirmation.

## Sombrero / LGPL rebuilding

Exact Sombrero 0.1.43 sources accompany this distribution under
`third_party/sombrero-0.1.43`. After QPM restore, select them with
`tools/use-local-sombrero.py`, then rebuild using README/BUILD_AND_TEST.
The port imposes no additional restriction on modifying this library or reverse
engineering the combined work for debugging such modifications. This statement
cannot override independent third-party terms. The build uses externally
restored game SDK headers and vendor libraries; full LGPL compliance should be
checked against the actual distributed combination and available rebuild inputs.

## Open provenance questions

1. The exact main-component licenses of BSML, Paper2, Kaleb, RapidjsonMacros and
   conditional-dependencies were not established in the earlier exact-cache audit.
   A GitHub license endpoint error is not proof that no license exists. Recheck
   exact tags/source and seek maintainer clarification where needed.
2. OVRLipSync is proprietary SDK material. The included header cites an older
   Oculus agreement; the applicable agreement and source of the exact binary
   require confirmation. Both published license texts are retained as evidence.
3. Native FinalIK-like code needs provenance clarification. Similar class/API
   names alone do not prove copying from commercial RootMotion code, and the root
   MIT notice alone does not prove authorization for any third-party translation.
4. The original shader AssetBundle, remaining UI icons, generated game interfaces
   and all internal Assimp/ChatPlex/Paper2 binary components are not fully attested.

These questions remain unresolved in this release preparation; version 1.1.58
does not resolve them merely by changing version metadata. Do not describe all
components as MIT, fully cleared or unrestricted. The earlier detailed English
report is retained separately as historical evidence, not a current clearance.

No user VRM avatars, copyrighted songs or Beat Saber application binaries are
included. Avatar owners must separately have the rights required for their models.
