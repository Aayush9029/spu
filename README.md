# spu

Check and update Swift package dependencies from the command line.

Parses `Package.swift`, fetches latest versions from GitHub in parallel, and lets you interactively update.

## Installation

```bash
brew install aayush9029/tap/spu
```

Or tap first:

```bash
brew tap aayush9029/tap
brew install spu
```

## Usage

```bash
spu                     # check current directory
spu ~/project           # check specific path
spu --check             # show table only, no prompt
spu --all               # find & auto-update all Package.swift files
```

## Options

| Flag | Description |
|------|-------------|
| `-h, --help` | Show usage info |
| `-v, --version` | Print version |
| `-c, --check` | Show version table only |
| `-a, --all` | Recursively find and update all |

## How it works

1. Parses `Package.swift` for `.package(url:..., from:...)` dependencies
2. Fetches latest release/tag from GitHub API (all repos in parallel)
3. Displays a version comparison table with update status
4. Prompts to select packages to update (or auto-updates with `--all`)
5. Applies in-place `sed` replacement in `Package.swift`

In `--all` mode, fetched versions are cached across files — shared dependencies are fetched only once.

## Requirements

- macOS (bash 3.2+, curl, python3)

## License

MIT
