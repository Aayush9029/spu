# spu

`spu` is a Bash CLI that checks the `.package(url:..., from:...)` dependencies in a `Package.swift` against the latest GitHub release or tag, and updates the versions. It ships through the Homebrew tap `aayush9029/tap`. Status: shipped.

## Commands

| Task | Command |
|------|---------|
| Run | `bin/spu ~/project` |
| Table only | `bin/spu --check` |
| Update all | `bin/spu --all` |
| Release | Load the `oss-cli-release` skill |

## How it works

- `bin/spu` is the full tool. It parses `Package.swift` with text tools, not with `swift package`.
- It calls the GitHub API for all packages in parallel. It uses `GITHUB_TOKEN`, or else `gh auth token`, or else no token (60 requests an hour).
- A cache in parallel arrays (`CACHE_KEYS`) replaces an associative array, because Bash 3.2 has none.

## Rules

- Flag a package only when the latest version is greater than the current version. Do not flag a current version that is ahead of the latest release.
- Fall back to a string comparison for a version that is not semver.
- Keep `VERSION` in `bin/spu` the same as the git tag. The tap formula is `../../homebrew-tap/Formula/spu.rb`.
