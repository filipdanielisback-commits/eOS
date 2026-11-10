# Moto G60 (hanoip): initial Linux feasibility notes

**eOS status:** Research only. No eOS build has been made or tested on this phone.

## Confirmed physical test device

- Product: Motorola Moto G60
- Exact model: `XT2135-2`
- Device family codename: `hanoip`
- Reported software build: `S2RIS32.32-20-9-9-2-3`
- Firmware identifier associated with this model/build: `XT2135-2_HANOIP_RETEU_12_..._XT2135-2-EUROPE...` (European retail firmware family)

The model/build combination matches a publicly indexed Motorola firmware identifier for the XT2135-2 European variant. This identifies the software branch, but does not establish compatibility with any experimental Linux image. Do not share IMEI, serial number, phone number, or account identifiers in project issues.

## Hardware identifiers to verify from reliable source material

- Reported SoC: Qualcomm SM7150 / Snapdragon 732G
- Reported GPU: Adreno 618

The exact model and reported build have been supplied by the device owner. RAM/storage configuration and board-level details remain to be checked against trustworthy documentation; do not infer them from the firmware string alone.

## External project found

[WaterResistantCoder/linux-hanoip-moto-g40-fusion](https://github.com/WaterResistantCoder/linux-hanoip-moto-g40-fusion) describes a mainline Linux v7.2 port for hanoip based on the SM7150 mainline kernel.

Its README and handoff report:
- Linux userspace boot
- Display using the MSM DRM stack
- Touch input
- Adreno 618 GPU initialization
- USB networking
- Plasma Mobile session
- Wi-Fi work in progress, blocked on missing SM7150 WPSS support
- Modem and voice calling not started

These are claims from the external project's own documentation. eOS has not independently reproduced or validated them, and support for the exact XT2135-2 variant/build has not been established.

## What this means for eOS

This is a meaningful lead: it suggests the Moto G60 may be a viable experimental mainline-Linux research target, rather than requiring an Android-derived OS as the only possible path.

It does **not** mean the phone is ready for eOS. eOS still needs its own userspace integration, shell, services, app platform, security model, and reproducible build process. Hardware gaps such as Wi-Fi, cellular, camera, sensors, audio, power management, and suspend/resume must be evaluated separately.

## Next safe research tasks

1. Review the external project's license, commit history, issue tracker, build instructions, and source provenance.
2. Compare its kernel and device-tree changes with upstream sources.
3. Record which components are upstream, locally patched, or dependent on proprietary firmware.
4. Check whether the external project's reported support specifically covers XT2135-2, not just the broader hanoip family.
5. Define a non-destructive test strategy and recovery plan before any device modification is considered.

Do not run external flashing scripts or install experimental images during this research phase. Preserve the phone's existing data and working operating system.

## References

- [External mainline Linux port](https://github.com/WaterResistantCoder/linux-hanoip-moto-g40-fusion)
- [hanoip Android device configuration](https://github.com/motorola-sm6150-devs/android_device_motorola_hanoip)
- [Motorola kernel source request for this exact XT2135-2 build](https://github.com/MotorolaMobilityLLC/kernel-msm/issues/574)
- [Plasma Mobile device-porting documentation](https://develop.kde.org/docs/plasma-mobile/porting/)
- [Mobian porting notes](https://wiki.debian.org/Mobian/Porting)
