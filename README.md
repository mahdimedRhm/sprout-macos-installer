# Sprout for macOS

Downloads for **Sprout** — run several branches of a project side by side, each in its own git worktree with its own database, Redis space, port and Herd site. Includes the `sprout-parallel` CLI and the Sprout menu bar app.

This repository only holds release downloads.

## Install

Requires macOS 14+ and git. Works on Apple silicon and Intel Macs.

```bash
curl -fsSL https://github.com/mahdimedRhm/sprout-macos-installer/releases/latest/download/install.sh | bash
```

This installs `sprout-parallel` into `~/.local/bin` and Sprout.app into `~/Applications`, after checking the download's SHA-256 checksum. It doesn't need `sudo` and doesn't edit your shell files.

Only the CLI:

```bash
curl -fsSL https://github.com/mahdimedRhm/sprout-macos-installer/releases/latest/download/install.sh | bash -s -- --cli-only
```

A specific version:

```bash
curl -fsSL https://github.com/mahdimedRhm/sprout-macos-installer/releases/latest/download/install.sh | SPROUT_VERSION=0.1.0 bash
```

## After installing

Sprout looks for your projects (git repositories) in `~/projects`. If yours are elsewhere, add to `~/.zshrc`:

```bash
export SPROUT_PROJECTS_ROOT="$HOME/code"
```

If `~/.local/bin` isn't on your PATH yet:

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
```

Then open a new terminal and start the app:

```bash
open ~/Applications/Sprout.app
```

## Update

Run the install command again.

## Uninstall

```bash
curl -fsSL https://github.com/mahdimedRhm/sprout-macos-installer/releases/latest/download/install.sh | bash -s -- --uninstall
```

Your worktrees, branches, databases and Herd sites are left alone.
