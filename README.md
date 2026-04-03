<p align="center">
  <img src="assets/icon.png" width="128" alt="spu">
  <h1 align="center">spu</h1>
  <p align="center">Check and update Swift package dependencies from the command line</p>
</p>

<p align="center">
  <a href="https://github.com/Aayush9029/spu/releases/latest"><img src="https://img.shields.io/github/v/release/Aayush9029/spu" alt="Release"></a>
  <a href="https://github.com/Aayush9029/spu/blob/main/LICENSE"><img src="https://img.shields.io/github/license/Aayush9029/spu" alt="License"></a>
</p>

<p align="center">
  <img src="assets/demo.gif" alt="spu demo">
</p>

## Install

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

## How it works

1. Parses `Package.swift` for `.package(url:..., from:...)` dependencies
2. Fetches latest release/tag from GitHub API (all repos in parallel)
3. Displays a version comparison table with update status
4. Prompts to select packages to update (or auto-updates with `--all`)

## License

MIT
