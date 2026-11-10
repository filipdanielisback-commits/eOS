# eOS technical architecture blueprint (draft)

**Status:** Working proposal; not an implementation specification  
**Target device for feasibility work:** Motorola Moto G60 XT2135-2 (`hanoip`)  
**Platform direction:** Mainline Linux kernel with an eOS-designed userspace is the preferred research path, not yet a final decision.

## 1. Product boundary

eOS is intended to be a distinct operating system, not an Android launcher or a lightly reskinned Android ROM. Its identity must come from eOS-owned system services, shell, settings, first-party apps, application model, update experience, and visual design.

Using the Linux kernel does not make the project an Android ROM. However, using Android's framework or Android userspace as a required foundation would change that claim and must be disclosed accurately.

## 2. Layered architecture

```text
Applications
  eOS first-party apps | third-party apps
Application platform
  SDK | package format | permissions | app lifecycle
eOS experience
  Shell | home/lock screen | notifications | quick settings
  compositor integration | accessibility | input methods
System services
  settings | accounts | telephony | connectivity | audio
  camera | location | power | updates | app installation
Hardware integration
  display | touch | GPU | audio | camera | sensors
  Wi-Fi | Bluetooth | modem | storage | power
Base userspace
  init/service manager | IPC | logging | core libraries
Linux kernel
  architecture | drivers | device tree | firmware interfaces
Boot and recovery
  firmware/boot chain | verified startup | recovery/update path
```

These are logical boundaries. The exact processes, libraries, and APIs still need design and prototyping.

## 3. Candidate foundation components

The following are candidates to evaluate, not selected dependencies:

| Area | Candidate direction | Decision still needed |
|---|---|---|
| Kernel | Upstream/mainline Linux where device support permits | Exact supported version, patches, device tree, firmware |
| Base userspace | A conventional Linux distribution base | Distribution, libc, package maintenance model |
| Init and service management | systemd or another maintained service manager | Boot integration, service supervision, update/recovery integration |
| IPC | D-Bus for system service APIs where appropriate | API conventions, permissions, compatibility guarantees |
| Graphics | Wayland with a mobile-oriented compositor | Compositor choice and hardware acceleration requirements |
| UI toolkit | Qt 6/QML is a candidate for a custom touch-first shell | Prototype performance, accessibility, developer experience |
| Audio | PipeWire ecosystem is a candidate | Audio routing, telephony integration, device support |
| Networking | Standard Linux networking services | Wi-Fi driver/firmware and mobile-data integration |
| App distribution | Signed eOS packages with a permission model | Format, sandbox, signing, repository metadata, rollback |
| Updates | Signed, atomic or rollback-capable system updates | Partition/storage strategy and recovery design |

Do not select a component solely because it is popular. Evaluate maintenance, security, licensing, device compatibility, and the size of the project needed to integrate it.

## 4. Hardware support is a separate layer

The eOS shell must not assume that a feature exists just because the UI has a button for it. Each hardware capability needs a service API, a device implementation, and a test.

Initial hardware capability groups:

- Display and graphics: modesetting, rendering, brightness, rotation
- Input: touchscreen, buttons, keyboard, vibration
- Connectivity: Wi-Fi, Bluetooth, USB, cellular data
- Telephony: modem control, calls, SMS, emergency-call constraints
- Media: audio playback/capture, camera, codecs
- Device state: battery, charging, thermal sensors, proximity, accelerometer
- Power: suspend/resume, wake sources, battery consumption
- Security: secure storage, credential handling, verified updates

A feature is marked **supported** only after it passes documented tests on the exact device variant. Otherwise use **reported**, **experimental**, **blocked**, or **not tested**.

## 5. eOS-owned software

The following should be designed as eOS components rather than assumed to exist already:

- eOS Shell: home screen, app switcher, lock screen, status area, notifications, quick settings
- Settings service and Settings app
- Application lifecycle and permission broker
- eApp Store client and repository service
- Update client and recovery interface
- First-party apps: Phone, eMessages, Camera, Notes, and device controls

The first prototype should not attempt all of these. Start with a minimal shell, settings surface, app launching, and a reliable way to update or recover the development system.

## 6. Application compatibility policy

Native Linux applications and Android applications are different targets. Android APK support is not automatic on a Linux userspace. Google apps and proprietary services have additional distribution, licensing, and service dependencies.

The eApp Store must display the actual app source, supported architecture/runtime, permissions, update channel, and compatibility status. It must not imply official endorsement or compatibility without authorization and testing.

## 7. Proposed prototype milestones

1. **Architecture prototype:** select a base userspace, service manager, IPC conventions, graphics stack, and UI toolkit after a written comparison.
2. **Build prototype:** create a reproducible build for a virtual or development environment; add automated lint and build checks.
3. **Shell prototype:** render a basic eOS shell on a supported Linux environment, with mock device services.
4. **Device feasibility:** only after source/license review, evaluate the Moto G60 kernel and hardware status using a documented, non-destructive plan.
5. **Hardware integration:** bring up one capability at a time and record test evidence.
6. **Application platform:** define package signing, app permissions, lifecycle, and update/rollback behavior before opening eApp Store to third-party apps.

## 8. Open decisions

- [ ] Choose base distribution/userspace and libc.
- [ ] Choose service manager and boot integration.
- [ ] Choose compositor and graphics stack.
- [ ] Prototype Qt 6/QML against at least one alternative before choosing the UI toolkit.
- [ ] Define eOS system-service APIs and IPC security.
- [ ] Define app package format, signing, sandbox, and permissions.
- [ ] Define update, rollback, and recovery architecture.
- [ ] Complete Moto G60 source, license, and exact-variant audit.
- [ ] Decide whether the first milestone targets a virtual environment before physical hardware.

## 9. Safety and project status

This document is a design proposal, not evidence of working software. No bootable eOS image, device driver integration, phone installer, or app runtime is claimed.

Do not modify the physical Moto G60 as part of architecture planning. Hardware experiments require a separately reviewed test plan, a verified recovery path, and appropriate experienced supervision.
