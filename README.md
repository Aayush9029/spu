# spu

Check and update Swift package dependencies from the command line.

## Install

```bash
brew install aayush9029/tap/spu
```

## Usage

```bash
spu                     # check current directory
spu ~/project           # check specific path
spu --check             # show table only, no prompt
spu --all               # find & auto-update all Package.swift files
```

## How it works

1. Parses `Package.swift` for `.package(url:..., from:...)` dependencies
2. Fetches latest release/tag from GitHub API (all repos in parallel)
3. Displays a version comparison table with update status
4. Prompts to select packages to update (or auto-updates with `--all`)

---

*More CLI tools: [`brew tap aayush9029/tap`](https://github.com/Aayush9029/homebrew-tap)*
