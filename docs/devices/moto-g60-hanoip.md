# Moto G60 (hanoip): initial Linux feasibility notes

**eOS status:** Research only. No eOS build has been made or tested on this phone.

## Identifiers to verify

- Product family: Motorola Moto G60 / Moto G40 Fusion
- Common device codename: `hanoip`
- Reported SoC: Qualcomm SM7150 / Snapdragon 732G
- Reported GPU: Adreno 618

The exact model number, region, board revision, RAM/storage configuration, and current software build on the physical handset still need confirmation. The user should share only the model number shown in Settings > About phone if needed; never share IMEI, serial number, phone number, or account identifiers.

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

These are claims from the external project's own documentation. eOS has not independently reproduced or validated them.

## What this means for eOS

This is a meaningful lead: it suggests the Moto G60 may be a viable experimental mainline-Linux research target, rather than requiring an Android-derived OS as the only possible path.

It does **not** mean the phone is ready for eOS. eOS still needs its own userspace integration, shell, services, app platform, security model, and reproducible build process. Hardware gaps such as Wi-Fi, cellular, camera, sensors, audio, power management, and suspend/resume must be evaluated separately.

## Next safe research tasks

1. Confirm the exact Moto G60 model number and regional variant from the phone's About screen.
2. Review the external project's license, commit history, issue tracker, build instructions, and source provenance.
3. Compare its kernel and device-tree changes with upstream sources.
4. Record which components are upstream, locally patched, or dependent on proprietary firmware.
5. Define a non-destructive test strategy and recovery plan before any device modification is considered.

Do not run external flashing scripts or install experimental images during this research phase. Preserve the phone's existing data and working operating system.

## References

- [External mainline Linux port](https://github.com/WaterResistantCoder/linux-hanoip-moto-g40-fusion)
- [hanoip Android device configuration](https://github.com/motorola-sm6150-devs/android_device_motorola_hanoip)
- [Plasma Mobile device-porting documentation](https://develop.kde.org/docs/plasma-mobile/porting/)
- [Mobian porting notes](https://wiki.debian.org/Mobian/Porting)
