# eOS

**eOS is an independent mobile-operating-system project.** Its goal is to create an original mobile experience, system services, first-party apps, and an app marketplace called **eApp Store**.

> **Development status:** Early planning and scaffolding. This repository does not yet contain a bootable operating system or a device-ready image. No phone is currently supported or verified.

## Project goals

- An original mobile interface, home screen, lock screen, notifications, and control center.
- First-party system apps such as Settings, Phone, eMessages, Camera, Notes, and eApp Store.
- Core services for networking, audio, display, power, updates, permissions, and device integration.
- eApp Store for discovering, installing, updating, and removing applications through authorized distribution channels.
- A secure update and application-permission model.
- Carefully researched device ports, starting with a single development target.

## Project principles

1. **Be honest about compatibility.** A device or app is supported only after it has been built, tested, and documented.
2. **Original work.** eOS will have its own visual identity and implementation; it will not copy proprietary iOS assets or branding.
3. **Security first.** Verified updates, least-privilege permissions, and responsible vulnerability handling are core requirements.
4. **Respect developers.** App distribution must follow developer authorization, licensing, and platform requirements.
5. **Build in stages.** A reliable booting foundation comes before broad device support or an app catalogue.

## Architecture status

The kernel, userspace, graphics stack, hardware-abstraction strategy, and application runtime are not yet selected. See [Architecture](docs/ARCHITECTURE.md). The project will not describe itself as Android-independent if an Android-derived platform becomes part of its foundation.

## Repository map

- `docs/` — architecture, device research, app ecosystem, and design decisions
- `apps/` — planned first-party application projects
- `system/` — planned operating-system services and shell
- `devices/` — per-device research and porting records
- `build/` — future reproducible build tooling

## Initial development sequence

1. Decide and document the platform architecture.
2. Set up a reproducible development environment and CI checks.
3. Build a minimal bootable development target.
4. Bring up display, input, storage, networking, audio, and power safely.
5. Develop the eOS shell and first-party apps.
6. Implement app installation, updates, and security controls.
7. Port to additional devices only after the first target is stable.

See [ROADMAP.md](ROADMAP.md) and [Device support](docs/DEVICE_SUPPORT.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Please do not submit unverified compatibility claims or device flashing instructions.

## License

A project-wide license has not been selected yet. Individual components may have different licensing requirements; do not assume all third-party code can be relicensed under one license.
