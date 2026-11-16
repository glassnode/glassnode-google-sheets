# Changelog

All notable changes, newest first. Format: [Keep a Changelog](https://keepachangelog.com/),
versions: [Semantic Versioning](https://semver.org/).

## [0.2.0] - 2026-11-16

### Added

- Environments: `src/Config.js` defines `prod` and `dev`. A deployment opts in to dev with
  the script property `GN_ENV=dev`; an unknown value is an error. The sidebar shows the
  environment when it is not production.

### Changed

- Production (`auth.glassnode.com`, `api.glassnode.com`) is the default environment.
- A session is tied to the environment that issued it, so switching environments signs
  the spreadsheet out.

## [0.1.1] - 2026-11-11

### Fixed

- `GN_METRIC` accepts only plain metric paths (letters, digits, `_` and `-` between
  slashes).
- A token refresh that finishes after a sign-out or a new sign-in no longer writes over
  that newer state. Sign-in and sign-out take the same lock as the refresh.

## [0.1.0] - 2026-11-10

### Added

- `GN_ASSETS` and `GN_METRIC` custom functions.
- Sign-in with the OAuth 2.0 device authorization flow, one session per spreadsheet.
- Sidebar and menu with **Refresh all formulas** and **Retry failed formulas**.
- Response caching, merging of identical requests and rate-limit handling.
