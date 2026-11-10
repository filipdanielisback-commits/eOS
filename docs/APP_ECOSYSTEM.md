# eOS application ecosystem

## eApp Store

eApp Store is planned as the primary place to discover, install, update, and remove applications on eOS. The store is not implemented yet.

Planned capabilities:
- Search, categories, featured apps, and developer pages
- App details, version history, screenshots, and permissions
- Install, update, rollback where safe, and uninstall
- Package signature verification
- Clear publisher identity and provenance
- Security review and abuse reporting
- Accessibility and parental-safety considerations

## Distribution and authorization

The store must use authorized distribution channels. Official developer apps may be listed or distributed only when the publisher's terms and permissions allow it. The project must not repackage proprietary apps or imply endorsement by their developers.

## Compatibility

An app's availability depends on its platform, runtime, architecture, graphics requirements, services, licensing, and developer policies. Compatibility must be tested app by app and device by device.

The project has not selected an application runtime or package format. Do not promise support for Android apps, Google services, games, or desktop software until a lawful, technically sound implementation has been selected and tested.

## Security requirements

- Verify signed packages before installation.
- Enforce app isolation and permission boundaries.
- Explain sensitive permissions to users.
- Support revocation of compromised signing keys.
- Keep update metadata and package provenance auditable.
- Provide a process for reporting malicious or vulnerable apps.
