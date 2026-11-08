# OnePlus SM6375-common (holi) — PenguinOS common device tree

> **⚠️ BUILD STATUS: UNTESTED — NOT BOOT-VERIFIED.**
> Configuration-audited only. No build or device test exists yet.

Common device tree for Qualcomm **SM6375 / holi**-based OnePlus devices on
**PenguinOS** (Android 17, branch `celerity`). Primary consumers:
OnePlus Nord CE 3 Lite 5G (`larry`) and OnePlus Nord N30 5G.

## Scope

- Board configuration (`BoardConfigCommon.mk`): boot header v3, DTB-in-bootimg,
  separated DTBO, `vendor_boot`-based recovery, 12 GiB super partition with
  dynamic partitions `odm product system system_ext vendor vendor_dlkm`.
- Product configuration (`sm6375.mk`): qcom-caf holi HAL wiring
  (`hardware/qcom-caf/sm8350/audio`), oplus hardware (`hardware/oplus`),
  virtual A/B OTA, emulated storage.
- Proprietary blob integration via generated
  `sm6375-common-vendor.mk` / `BoardConfigVendor.mk`.

## Kernel

- `LineageOS/android_kernel_oneplus_sm6375` @ `lineage-24.0`
- Defconfig: `vendor/holi-qgki_defconfig` + `vendor/debugfs.config`

## Dependencies

Same set as the `larry` device tree — see the `larry` repository README and
the `larry-penguin.xml` manifest example in the release package.

## Branch information

- **`celerity`** — lineage-24.0 content + publication commits (README, LICENSE).
- Upstream: `LineageOS/android_device_oneplus_sm6375-common` (`lineage-24.0`).

## Credits & upstream attribution

- **LineageOS Project** — original tree: **Vivekachooz** (lead),
  **Michael Bestas**, **LuK1337** (and upstream contributors).
- **AOSPA / Project PenguinOS** — ROM platform.

## Known issues

- **Not boot-tested.**
- NFC RF config for panel variant 22872 absent from blob set (see `larry` README).

## Build status

```
[ UNTESTED / NOT BOOT-VERIFIED ]
Configuration audit: PASSED (parses as part of aospa_larry graph)
Build:               NOT ATTEMPTED
Device boot:         NOT ATTEMPTED
```
