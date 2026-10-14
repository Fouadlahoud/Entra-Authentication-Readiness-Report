# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.0] - 2026-10-14

### Fixed

- SMS and voice authentication steps are now matched by name pattern (`SMS`, `Text message`, `Voice`, `Voice call`, `Phone call`) instead of exact `SMS`/`Voice`, so live tenants that report descriptive method names no longer produce an empty migration list.
- Removed unused registration lookup tables.

### Changed

- Priority logic now distinguishes phishing-resistant registration (FIDO2, device-bound passkey, Windows Hello for Business) from the `IsPasswordlessCapable` flag, and recognises Authenticator/OTP as a non-phone fallback.
- Administrators with successful SMS or voice use are Critical; administrators with phone methods and no phishing-resistant credential are High even without observed use.
- Users with a phone registered but a non-phone method preferred and no telephony use are Low instead of High.
- Manifest schema 1.1: `ActivePhoneUsersNotPasswordlessCapable` renamed to `ActivePhoneUsersNoPhishingResistant`.

### Added

- `PhishingResistantRegistered` and `StrongNonPhoneRegistered` columns in the registration inventory, action list, and HTML action table.
- `TelephonyType` column in the event-level export.
- Warnings when no sign-ins are returned, when data covers only 7 of the requested days (Entra ID Free retention), and when steps were processed but no telephony method name was recognised.
- Interactive-only sign-in coverage documented in the script help, README, and HTML report.

## [1.0.0] - 2026-10-14

### Added

- Microsoft Entra authentication-method registration inventory.
- Sign-in authentication-step collection with configurable query windows.
- Per-user and tenant-wide authentication-method usage summaries.
- Prioritized SMS and voice migration action list.
- Executive HTML report and JSON run manifest.
- Optional event-level and authentication-method-detail exports.
- Offline reporting mode with fictional sample data.
- Cross-version smoke tests and GitHub Actions validation.

[1.1.0]: https://github.com/fredlahoud/Entra-Authentication-Readiness-Report/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/fredlahoud/Entra-Authentication-Readiness-Report/releases/tag/v1.0.0
