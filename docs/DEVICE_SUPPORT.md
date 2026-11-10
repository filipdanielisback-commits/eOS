# Device support

## Current status

**No phone is currently supported, ported, or tested by the eOS project.** The models below are research targets only. Similar product names can have different regional variants, chipsets, partition layouts, and bootloader policies.

| Device target | Status | Next research |
|---|---|---|
| Motorola Moto G60 | Promising external Linux prototype found; not an eOS port | Verify exact model variant and independently review the reported mainline port |
| Redmi Note 13 Pro 5G | Research target | Confirm exact model/variant, codename, chipset, kernel sources, boot chain, and existing Linux support |
| POCO X6 5G | Research target | Confirm exact model/variant, codename, chipset, kernel sources, boot chain, and existing Linux support |
| Xiaomi 15 | Research target | Confirm exact model/variant, codename, chipset, kernel sources, boot chain, and existing Linux support |

## Moto G60 research notes

The Moto G60 is commonly grouped with the Moto G40 Fusion under the codename **hanoip**. Community device-tree sources identify the platform as Qualcomm SM7150 / Snapdragon 732G with Adreno 618 graphics. Exact regional model numbers and board revisions still need confirmation.

A public third-party project, [WaterResistantCoder/linux-hanoip-moto-g40-fusion](https://github.com/WaterResistantCoder/linux-hanoip-moto-g40-fusion), reports a mainline Linux v7.2-based port for the Moto G40 Fusion / G60. Its README reports booting to userspace, display, touch, Adreno 618 GPU initialization, USB networking, and Plasma Mobile; it lists Wi-Fi as incomplete and modem/calls as not started. These are the upstream project's own claims, not eOS test results or an independent verification.

Useful background:
- [hanoip device-tree project](https://github.com/motorola-sm6150-devs/android_device_motorola_hanoip) — Android-oriented device configuration; not itself a mainline Linux port.
- [KDE Plasma Mobile device-porting notes](https://develop.kde.org/docs/plasma-mobile/porting/) — explains why Android vendor drivers and hardware abstraction layers do not automatically work in a conventional Linux userspace.

**Important:** eOS has not built, booted, or tested any image on the Moto G60. The existence of an external prototype is encouraging research evidence, not a supported eOS release. Do not run third-party flashing scripts or install experimental images as part of this research. Device modification can erase data or make a phone unusable; keep research non-invasive until a reviewed, device-specific test plan and recovery plan exist.

Before treating the external work as a dependency, review its license, source provenance, build reproducibility, maintenance status, and technical changes. Do not copy code or proprietary firmware without checking the applicable licenses and permissions.

## Porting checklist

For each exact hardware variant, research and record:
- Manufacturer model number and regional variant
- Device codename and SoC
- Bootloader and verified-boot behavior
- Kernel source availability and maintenance status
- Device tree and required firmware
- Display, touch, GPU, audio, camera, sensors, and power support
- Wi-Fi, Bluetooth, GNSS, and cellular modem support
- Storage layout, encryption, and recovery strategy
- Known upstream support in mobile Linux projects
- Reproducible build and test evidence

## Support levels

- **Research target:** only identified for investigation.
- **External prototype:** a third-party project reports progress; eOS has not verified it.
- **Build target:** an eOS build configuration exists; this does not prove it boots.
- **Boot-tested:** a documented eOS build reaches userspace on the exact variant.
- **Basic hardware:** essential input, display, storage, and networking have been tested.
- **Experimental:** broader functions work but important limitations remain.
- **Supported:** repeatable builds, tested updates/recovery, and documented maintenance.

A successful build is not the same as a working phone port. Never flash an image intended for a different model or variant.
