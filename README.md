# Homebrew tap for [OpenCodeRust](https://github.com/vakandi/opencode-rust)

```bash
brew install vakandi/tap/opencode-rust
```

## What it does

Installs the `opencode` binary and links `opr` alongside it. The formula builds from
source, so the first install needs a Rust toolchain — Homebrew fetches that as a build
dependency.

## Manual install

```bash
brew tap vakandi/tap
brew install opencode-rust
```

## After install

```bash
opr                      # interactive TUI
opr run "your task"      # one prompt, runs to completion
opr serve --port 3000
```

`opr` is a symlink to `opencode` here, not a dispatcher. A global flag
(`opr --some-flag`) is forwarded unchanged and will be rejected — name the subcommand
instead: `opr tui --some-flag`. The npm package behaves differently; its `opr` *is* a
dispatcher.

Configure a provider key before your first run, e.g. `export ANTHROPIC_API_KEY=...`.