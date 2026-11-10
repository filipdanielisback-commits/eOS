# Moto G60 Linux port: source and compatibility audit

**Audit status:** Not yet complete  
**eOS target handset:** Motorola Moto G60, model `XT2135-2`  
**Device family:** `hanoip`  
**Reported software build:** `S2RIS32.32-20-9-9-2-3`

## Scope

This audit evaluates whether the external `linux-hanoip-moto-g40-fusion` work can be used as a technical reference for an independent eOS port. It does not assume that eOS is based on that project, that the project supports every hanoip variant, or that its reported features have been independently reproduced.

## Initial public information

A GitHub topic listing describes the external project as a mainline Linux port for the Moto G40 Fusion / G60 (hanoip, SM7150-AC), with Plasma Mobile, touch, GPU, and USB networking reported, and WCN3990 Wi-Fi marked as work in progress. The listing showed an update on 2026-11-08.

These are project-description claims, not independent test results. The exact `XT2135-2` variant and the reported software build have not yet been confirmed as tested by that project.

## Audit checklist

### 1. Provenance and licensing

- [ ] Confirm the repository's current visibility, owner, default branch, and maintenance status.
- [ ] Locate and read the repository's explicit license file or license declaration.
- [ ] Record copyright notices and licenses for bundled or copied components.
- [ ] Identify upstream projects, forks, patches, and third-party contributors.
- [ ] Do not copy code into eOS until its license and provenance are understood.
- [ ] If no clear license is present, treat the code as unavailable for reuse unless the author clarifies permission.

### 2. Kernel and device support

- [ ] Identify the exact kernel base and version.
- [ ] Record the upstream commits and locally maintained patch set.
- [ ] Identify the device tree and confirm its board/variant coverage.
- [ ] Check whether the project explicitly names model XT2135-2.
- [ ] Separate upstream-supported drivers from experimental or out-of-tree drivers.
- [ ] Identify required proprietary firmware and its redistribution restrictions.

### 3. Hardware feature evidence

For each item, record the evidence source, tested device variant, test date, and known limitations.

| Component | Current eOS audit status |
|---|---|
| Display / DRM | External project reports support; independently unverified |
| Touch input | External project reports support; independently unverified |
| GPU / Adreno 618 | Initialization reported; full acceleration unverified |
| USB networking | Reported; independently unverified |
| Wi-Fi / WCN3990 | Reported as work in progress |
| Cellular modem / calls | Reported as not started |
| Camera | Not verified |
| Audio | Not verified |
| Bluetooth | Not verified |
| Sensors / location | Not verified |
| Battery / charging | Not verified |
| Suspend / resume | Not verified |
| Hardware encryption / secure storage | Not verified |

### 4. Build and reproducibility

- [ ] Determine whether documented builds can be reproduced from source.
- [ ] Record required toolchains, dependencies, and source revisions.
- [ ] Check whether build outputs are traceable to a specific source commit.
- [ ] Review build scripts statically before considering any execution.
- [ ] Do not run device-modification, flashing, or installation scripts as part of this audit.

### 5. Security and maintenance

- [ ] Review default accounts, credentials, remote access, debug settings, and privileged services.
- [ ] Check how updates and security fixes are delivered.
- [ ] Identify project maintainers and recent review activity.
- [ ] Record open issues and known security limitations.
- [ ] Do not reuse insecure development defaults in eOS.

## Decision gate

The external work may be used as a reference only after the provenance, license, kernel base, device coverage, and security review are documented. Reuse of source code requires a compatible, explicit license. Hardware support claims must be independently validated before being marked as supported by eOS.

## Safety boundary

This phase is documentation and source review only. Do not modify the phone, unlock its bootloader, flash images, or run third-party installation scripts. Keep the existing operating system and personal data intact.

## References

- [External hanoip mainline Linux project](https://github.com/WaterResistantCoder/linux-hanoip-moto-g40-fusion)
- [GitHub topic listing that surfaced the project](https://github.com/topics/motorola?l=python&o=desc&s=updated)
- [Plasma Mobile porting documentation](https://develop.kde.org/docs/plasma-mobile/porting/)
- [Mobian porting notes](https://wiki.debian.org/Mobian/Porting)
