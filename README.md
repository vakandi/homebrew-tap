# Homebrew tap for [OpenCodeRust](https://github.com/vakandi/opencode-rust)

```bash
brew install vakandi/tap/opr
```

## What it does

Installs the `opencode` binary and links `opr` alongside it. The formula builds from
source, so the first install needs a Rust toolchain — Homebrew fetches that as a build
dependency.

## Manual install

```bash
brew tap vakandi/tap
brew install opr
```

## After install

```bash
opr                  # interactive TUI
opr run "your task"  # one prompt, runs to completion
opr serve --port 3000
```

`opr` with no subcommand opens the TUI. `opr --some-flag` also opens the TUI — only a
known subcommand is forwarded verbatim.

Configure a provider key before your first run, e.g. `export ANTHROPIC_API_KEY=...`.