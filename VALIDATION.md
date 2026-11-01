# Validation scope — 1.1.58

The final binary is rebuilt from beta.5.8. Functional solver/rendering algorithms,
assets and dependency versions remain unchanged; release version strings and
publication/package documentation change. The comparison log lists every changed file.

## Automated evidence

The release archive includes the actual compiler/linker log, manifest and packaging
log, ELF/subsystem audit, host guard/arm/crouch/spine/load-order/material test logs,
package checksums and a source patch against beta.5.8. Read those logs for exact
results. Test output is not a substitute for device validation.

The arm regression suite covers independent hands, shoulder/no-shoulder rigs,
scale variations, lowered arms with 25% extension, crouch combinations, excess
reach while crouched and whole-body scenarios. Its negative control reproduces
the old pre-spine false-release bug.

## User observations from earlier builds

The owner reported a successful load on Quest 3, effective Match Armspans fitting,
usable crouching and removal of observed bloom bleed-through. Residual distortion
around footwear was accepted for further testing. The +30% tuning was requested
for beta.5.8; a full final-version device regression was not recorded by the builder.

## Required Quest smoke tests

- Cold launch, load an avatar, change avatars, restart: no crash or black materials.
- Match Armspans calibration: model scale and hand alignment at normal reach.
- Lower arms, lift arms, crouch: no false detach; real excess reach releases each hand.
- Return within reach: smooth independent reconnection, no saber tracking changes.
- Settings sliders: stable avatar pose and saved settings after restart.
- Mirror, normal gameplay and third-person replay with the actual replay mod.
- Bright environments: bloom does not wash out or bleed through opaque surfaces.
- Shockwave-heavy scenes: inspect shoes; complete removal is not guaranteed.
- Expressions, blinking, spring bones, VMC/full-body and varied VRM rigs.

No FPS, memory, battery, all-rig compatibility or Quest GPU guarantee is made.
