# Security policy

Security is a core requirement for eOS. This policy will be expanded as the project gains executable components and release infrastructure.

## Current status

eOS is an early-stage project and is not suitable for use as a daily operating system. There are no production releases or supported phone images at this time.

## Reporting a vulnerability

For a suspected security issue, contact the repository owner privately through GitHub's supported private vulnerability reporting feature, if enabled. Include:
- A concise description of the issue
- Affected commit, component, or build
- Reproduction context that does not expose other people's data
- Potential impact

Do not include secrets, personal data, or weaponized proof-of-concept material in a public issue.

## Security goals

- Verify package and system-update signatures before installation.
- Use least privilege and isolate applications.
- Protect user data at rest and in transit.
- Keep privileged services small and auditable.
- Provide safe update rollback and recovery.
- Publish security fixes and release notes.
- Never request or store users' account passwords or private signing keys in the repository.

## Device testing

Experimental images can cause data loss or leave hardware unusable if used incorrectly. Any future installation documentation must clearly identify the exact tested device variant, prerequisites, limitations, and recovery path. No installation procedure should be published as safe until it has been validated.
