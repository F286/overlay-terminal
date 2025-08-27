# Overlay Terminal for VS Code

[![Latest release](https://img.shields.io/github/v/release/F286/overlay-terminal?sort=semver)](https://github.com/F286/overlay-terminal/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/F286/overlay-terminal/latest/total)](https://github.com/F286/overlay-terminal/releases/latest)
[![CI](https://github.com/F286/overlay-terminal/actions/workflows/release.yml/badge.svg)](https://github.com/F286/overlay-terminal/actions/workflows/release.yml)

A tiny VS Code extension that opens a terminal **in a new window** using any of your configured terminal profiles. When the shell exits the window closes and focus returns to the editor (sending `Esc` for VSCodeVim users).

> Requires VS Code **1.82+**

## Install

### From the latest release
1. Download the `.vsix` from the [latest release](https://github.com/F286/overlay-terminal/releases/latest).
2. Install it:
   ```bash
   code --install-extension ./overlay-terminal.vsix
   ```

### From source
```bash
npm install --ignore-scripts
npm run build
npm run package
# overlay-terminal.vsix will appear in the repo root
```

## Usage

* Command Palette: `Overlay Terminal: Pick Profile`.
* Open a specific profile with a keybinding:
  ```jsonc
  {
    "key": "ctrl+`",
    "command": "overlayTerminals.openProfile",
    "args": { "profileName": "zsh" }
  }
  ```

The extension uses your OS specific `terminal.integrated.profiles.*` setting and moves the terminal into a separate window with `workbench.action.terminal.moveIntoNewWindow`.

## CI / Releases

* Every push to `main` builds the extension and uploads the packaged `.vsix` as a workflow artifact.
* Pushing a tag like `v0.2.0` also creates a GitHub release with the `.vsix` attached.

## Commands

* `overlayTerminals.openProfile` – Overlay Terminal: Open Profile
* `overlayTerminals.pickProfile` – Overlay Terminal: Pick Profile
