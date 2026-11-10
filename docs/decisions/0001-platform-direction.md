# ADR 0001: Platform direction for eOS

- **Status:** Proposed; awaiting device feasibility research
- **Date:** 2026-11-10
- **Decision owners:** eOS maintainers

## Context

eOS aims to be an independent mobile operating-system project with its own user experience, system services, first-party applications, and eApp Store. The project does not want to be merely an Android launcher or a lightly reskinned Android ROM.

A phone operating system also needs working hardware support: boot, kernel, display, touch, graphics, storage, audio, networking, power management, sensors, cameras, and potentially cellular telephony. The available drivers and firmware on each device strongly affect the feasible platform choice.

## Options considered

### A. Linux kernel with an eOS-designed userspace

Use the Linux kernel and build the eOS platform above it: service management, hardware integration, compositor, shell, applications, package management, and update infrastructure.

**Advantages**
- Does not require Android's application framework or Android userspace.
- Mature kernel and broad ecosystem of open-source tools.
- Supports a genuinely distinct eOS userspace and product identity.

**Risks**
- Phone-specific hardware may lack upstream Linux drivers.
- Proprietary firmware and vendor interfaces may limit functionality.
- Android phone support cannot be assumed; each exact device variant requires investigation and testing.
- Android application compatibility is not automatic.

### B. Android-derived platform

Reuse Android's kernel/device enablement and replace or customize major user-facing components.

**Advantages**
- Often a more practical route to existing Android phone hardware.
- May provide access to existing vendor drivers and hardware interfaces.

**Risks**
- This is Android-derived and does not meet the project's strict independence goal.
- Android app compatibility, Google services, and app-store distribution still involve technical and licensing constraints.

### C. New kernel and platform from scratch

Develop a new kernel, drivers, userspace, graphics, networking, security, and application ecosystem.

**Advantages**
- Maximum theoretical control and independence.

**Risks**
- Extremely large engineering and maintenance burden.
- Not a realistic starting point for a small initial phone prototype.

## Proposed direction

Investigate **Option A: Linux kernel with an eOS-designed userspace** as the preferred direction, subject to a hardware feasibility audit of the first development target.

This is a proposal, not a final architecture commitment. Do not mark the platform as selected until the first target's exact hardware variant, boot process, kernel support, graphics, connectivity, and recovery constraints have been researched.

## Decision gates

Before accepting this proposal as final:

1. Choose one phone that the project can physically test.
2. Identify its exact model number, regional variant, and device codename.
3. Check available kernel sources and upstream driver support.
4. Assess display, touch, GPU, audio, storage, Wi-Fi, Bluetooth, camera, sensors, battery, and modem support.
5. Document the boot and recovery situation without attempting unvalidated flashing.
6. Compare the effort against a known Linux mobile reference platform.
7. Record the final decision and explain any compromises.

## Consequences

If Option A is confirmed:
- eOS must not depend on Android's framework as its core userspace.
- eOS will need its own service integration and application platform.
- The first device should be selected for achievable Linux hardware support, not just popularity.
- Android apps and Google apps must be treated as separate compatibility projects, not assumed features.
- Additional phone models will be added only after individual porting and testing.

## Revisit this decision when

- Device research shows the chosen target cannot support the required Linux stack.
- A major change in upstream kernel or mobile hardware support makes another route materially more feasible.
- The project requirements change and the trade-offs are explicitly accepted.
