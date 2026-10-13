# Homebrew tap

```bash
brew install vakandi/tap/opencode-rust   # CLI
brew install --cask vakandi/tap/eliatopbar   # menu bar app
```

## EliaTopBar (cask)

```bash
brew tap vakandi/tap
brew install --cask eliatopbar
```

Installs `EliaTopBar.app` into `/Applications`. It is a menu bar app
(`LSUIElement`), so there is no Dock icon — look for it next to the system
status items.

EliaTopBar is ad-hoc signed and not notarized. The cask removes the quarantine
flag for you; if macOS still refuses to open it:

```bash
xattr -dr com.apple.quarantine /Applications/EliaTopBar.app
```

`brew uninstall --cask eliatopbar` leaves your agent photos alone. Add `--zap`
to remove `~/Library/Application Support/EliaTopBar` as well.

The cask is versioned in the app repo and synced to this tap on release, so the
`sha256` here always matches the published DMG:
https://github.com/vakandi/Elia-Topbar

---

## OpenCodeRust (formula)

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