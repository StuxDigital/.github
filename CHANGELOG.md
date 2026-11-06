# Changelog

All notable changes to Stux.Digital's `.github` organization repository are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Date Versioning](https://datevers.ing) since v26.10.23 (`YY.MM.DD`, the UTC release date, with `-1`, `-2`… for later releases the same day); earlier releases used [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## v26.11.06-1

### Changed

- Work happens on a `test` branch: changes reach `main` only through a pull request from `test`, and release commits and tags are made on `test`. `README.md` and `CONTRIBUTING.md` (a new Branches section) say so
- `CONTRIBUTING.md`'s development workflow starts from `test` and opens the pull request from `test` into `main`

## v26.11.06

### Added

- The organisation profile lists Stux.Digital's projects by their full names: **Stux.Digital Clients**, **Stux.Digital Status**, **Stux.Digital Clientpage**, **Soonpage**, **Maintenancepage** and **GitHub Pages Redirect**, each with its site. It links stux.digital and clients.stux.digital, and a new Service Status section links status.stux.digital
- `CONTRIBUTING.md` says how to keep the profile current

### Changed

- The logo and footer icons in the profile and `README.md` use the light/dark `<picture>` style, so they read on both GitHub themes
- `README.md` describes the activity stats workflow rather than community files the repo doesn't have
- `CONTRIBUTING.md` no longer asks for an `[Unreleased]` changelog section, which Date Versioning releases don't use

### Removed

- The empty, misplaced `[Unreleased]` heading in this changelog

## v26.10.23

### Added

- `tests/version.sh`, which checks that `VERSION.md` is a valid Date Version, a real calendar date not in the future, and the same as the newest entry in this changelog

### Changed

- Switched from Semantic Versioning to [Date Versioning](https://datevers.ing): releases are numbered by their UTC release date as `YY.MM.DD`, with `-1`, `-2`… for later releases the same day. This release follows v1.0.1
- `commit.sh` and `commit.bat` refuse a `VERSION.md` that isn't a valid Date Version or is dated in the future (UTC), and warn when it's dated before today
- `README.md` and `CONTRIBUTING.md` describe Date Versioning and the release steps

## [1.0.1] - 2026-10-08
### Added
- Bluesky and LinkedIn badges (`bsky.app/profile/stux.digital`, `linkedin.com/company/stuxdigital`) in the "Connect with Us!" section, alongside the existing GitHub followers badge, matching the other Stux.Group brand profiles.

## [1.0.0] - 2026-10-05
### Added
- Initial Stux.Digital org profile (`profile/README.md`) with the welcome, mission, contact and "Our Activity" sections and the shared Stux.Group footer, matching the other Stux.Group brand `.github` repos.
- `generateMetrics.yml` workflow that renders the "Our Activity" stats onto the `metrics` branch.
- `README.md`, `CONTRIBUTING.md`, `VERSION.md`, `commit.sh`/`commit.bat` and `.gitignore`, following the standard release flow.
