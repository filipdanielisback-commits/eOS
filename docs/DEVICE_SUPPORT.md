# Device support

## Current status

**No phone is currently supported, ported, or tested by this project.** The models below are research targets only. Similar product names can have different regional variants, chipsets, partition layouts, and bootloader policies.

| Device target | Status | Next research |
|---|---|---|
| Motorola Moto G60 | Research target | Confirm exact model/variant, codename, chipset, kernel sources, boot chain, and existing Linux support |
| Redmi Note 13 Pro 5G | Research target | Confirm exact model/variant, codename, chipset, kernel sources, boot chain, and existing Linux support |
| POCO X6 5G | Research target | Confirm exact model/variant, codename, chipset, kernel sources, boot chain, and existing Linux support |
| Xiaomi 15 | Research target | Confirm exact model/variant, codename, chipset, kernel sources, boot chain, and existing Linux support |

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
- **Build target:** a build configuration exists; this does not prove it boots.
- **Boot-tested:** a documented build reaches userspace on the exact variant.
- **Basic hardware:** essential input, display, storage, and networking have been tested.
- **Experimental:** broader functions work but important limitations remain.
- **Supported:** repeatable builds, tested updates/recovery, and documented maintenance.

A successful build is not the same as a working phone port. Never flash an image intended for a different model or variant.
