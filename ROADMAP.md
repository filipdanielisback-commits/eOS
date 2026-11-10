# eOS roadmap

This roadmap describes goals, not completed features. Items move to **Done** only after code, tests, and evidence are available.

## Phase 0 — Project foundation

- [x] Create the public repository and initial documentation.
- [ ] Choose the kernel and userspace architecture.
- [ ] Record licensing and third-party dependency policy.
- [ ] Define a reproducible build host and toolchain.
- [ ] Add continuous integration for formatting, static checks, and tests.

## Phase 1 — Minimal bootable development target

- [ ] Select one development device or supported reference platform.
- [ ] Document boot chain, kernel, firmware, partition layout, and recovery constraints.
- [ ] Produce a reproducible boot image for the selected target.
- [ ] Reach a stable early userspace.
- [ ] Add serial/logging and safe recovery diagnostics.

## Phase 2 — Hardware and platform services

- [ ] Display and graphics
- [ ] Touch and input
- [ ] Storage and encryption
- [ ] Wi-Fi and Bluetooth
- [ ] Audio
- [ ] Power management and battery reporting
- [ ] Camera and sensors
- [ ] Cellular modem and telephony, where supported

## Phase 3 — eOS shell and system apps

- [ ] Setup Assistant
- [ ] Home Screen and Lock Screen
- [ ] Status Bar and Control Center
- [ ] Notifications
- [ ] Settings
- [ ] Camera, Notes, Phone, and eMessages
- [ ] Accessibility, localization, and input methods

## Phase 4 — eApp Store and application platform

- [ ] Choose a package format and application sandbox model.
- [ ] Implement package signing and signature verification.
- [ ] Implement install, update, rollback, and uninstall flows.
- [ ] Build the eApp Store client and repository service.
- [ ] Define developer publishing and app review policies.
- [ ] Evaluate compatibility runtimes without promising unsupported apps.

## Phase 5 — Reliability and device expansion

- [ ] Automated boot and regression testing
- [ ] Battery, thermal, performance, and stability testing
- [ ] Security review and update recovery tests
- [ ] Add further device ports one at a time
- [ ] Publish release notes and verified compatibility matrices

## Release labels

- **Prototype:** experimental code; not for daily use.
- **Developer preview:** boots on explicitly listed test hardware; major features may be missing.
- **Beta:** feature-complete for listed hardware but still undergoing reliability and security testing.
- **Stable:** documented support, repeatable builds, tested updates, and an established security process.
