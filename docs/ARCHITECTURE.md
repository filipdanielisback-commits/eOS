# eOS architecture

## Status: undecided

The project wants an original operating system rather than a reskinned launcher. The underlying platform has not yet been selected. This decision must be made before committing to a kernel, graphics stack, application ABI, or device-porting workflow.

## Candidate directions

### Independent mobile Linux userspace

Use the Linux kernel with a mobile-focused userspace, compositor, shell, and system services designed for eOS. This can provide an independent user experience and userspace, but phone hardware support may be difficult where mainline Linux drivers or firmware are unavailable.

### Android-derived hardware-enablement base

Reuse Android's existing kernel, hardware interfaces, and device enablement while replacing major user-facing components. This can make existing Android phone hardware more reachable, but it is Android-derived and must not be marketed as a completely Android-independent OS.

### New kernel and platform from scratch

This offers the greatest theoretical independence but is far beyond the practical scope of an initial phone prototype. It would require a complete driver, kernel, userspace, graphics, networking, security, and application ecosystem effort.

## Required decision record

Before selecting a direction, compare:
- Whether the target devices have usable kernel sources and hardware support
- Boot-chain and verified-boot constraints
- GPU, display, touch, audio, camera, sensors, Wi-Fi, Bluetooth, and modem support
- Update and recovery design
- Application framework and package format
- Security maintenance and licensing
- Build reproducibility and long-term maintainability

## Core conceptual layers

The eventual architecture is expected to separate:
1. Boot and early startup
2. Kernel and hardware support
3. Core userspace and service manager
4. Hardware abstraction and device services
5. Graphics compositor and eOS shell
6. System applications
7. Application packaging, permissions, and eApp Store
8. Secure update and recovery system

These are planning boundaries, not implemented components.
