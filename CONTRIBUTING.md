# Contributing to eOS

Thanks for your interest in eOS. The project is at an early stage, so clear research and small, reviewable changes are especially valuable.

## Before opening a change

1. Check existing issues and documentation.
2. Describe the problem and the intended result.
3. Keep changes focused and explain how they were tested.
4. Do not claim a device or app works unless you have reproducible test evidence.

## Code expectations

- Prefer readable, maintainable code over clever shortcuts.
- Add tests for behavior that can be tested automatically.
- Document build requirements and third-party dependencies.
- Do not commit passwords, access tokens, private keys, personal data, or proprietary firmware.
- Respect upstream licenses and copyright notices.
- Do not include proprietary app binaries or branding without authorization.

## Device work

Device support is hardware-specific. Record the exact model and hardware variant, relevant kernel and firmware versions, known limitations, test results, and recovery considerations. Never treat a device as supported based only on a successful compile.

## Security issues

Please do not publish exploitable vulnerability details in a public issue. Follow [SECURITY.md](SECURITY.md).

## Pull requests

A useful pull request includes:
- What changed and why
- How it was tested
- Known limitations
- Screenshots or logs when they clarify a UI or hardware change (remove personal information first)
