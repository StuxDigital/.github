# Contributing

Thanks for your interest in contributing to this project.

## Development Workflow

1. Work on `test`, or a feature branch off it (see Branches and going live).
2. Make focused, well-described commits.
3. Describe your changes in a new release entry at the top of `CHANGELOG.md` (see Versioning below).
4. Open a pull request from `test` into `staging`, then one from `staging` into `main` (see Branches and going live).

## Keeping the profile current

`profile/README.md` is the org's public face, so update it whenever the org changes:

- List every public StuxDigital repository in **Our Projects**, by its full name ("Stux.Digital Status", not "Status"), with its site. Leave private repos out, and remove retired ones
- Keep the status page link in **Service Status** pointing at [status.stux.digital](https://status.stux.digital)
- Use the light/dark `<picture>` logo and icons from `global.media.stux.digital`, not a single image

## Branches and going live

- **`main` is what's live.** Nothing is pushed to it directly: it only changes when a pull request from `staging` is merged, and it needs CI to pass.
- **`staging` is the last check before live.** It only changes when a pull request from `test` is merged. It isn't deployed anywhere of its own; deploys stay on `main`.
- **Work happens on `test`**, or on a feature branch off `test` that's merged back into it. Releases are made on `test` too; `commit.sh` / `commit.bat` refuse to run on `staging` or `main`.
- **Going live:** push `test` with its tag (`git push origin test --tags`), open a pull request into staging (`gh pr create --base staging --head test`), check staging once it's merged, then open one from staging into main (`gh pr create --base main --head staging`). Leo reviews and merges both.

## Versioning

This project uses [Date Versioning](https://datevers.ing). To release:

1. Add a `## vYY.MM.DD` entry at the top of `CHANGELOG.md`, with its sections in this order: Added, Changed, Fixed, Removed, Security, Deprecated.
2. Set `VERSION.md` to the same bare version (no `v`): today's **UTC** date as `YY.MM.DD`, or `YY.MM.DD-1`, `-2`… for later releases the same UTC day. Never a future date. Use UTC, not local time: just after midnight in the UK it is still the previous day in UTC.
3. Run `bash tests/version.sh`.
4. Run `./commit.sh` (or `commit.bat` on Windows). It checks the version, commits and tags `vYY.MM.DD`, and never pushes.
