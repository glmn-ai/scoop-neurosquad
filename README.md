# NeuroSquad for Scoop

[![Tests](https://github.com/glmn-ai/scoop-neurosquad/actions/workflows/ci.yml/badge.svg)](https://github.com/glmn-ai/scoop-neurosquad/actions/workflows/ci.yml) [![Excavator](https://github.com/glmn-ai/scoop-neurosquad/actions/workflows/excavator.yml/badge.svg)](https://github.com/glmn-ai/scoop-neurosquad/actions/workflows/excavator.yml)

A [Scoop](https://scoop.sh) bucket for [NeuroSquad](https://neurosquad.ai/) — a desktop canvas for
AI coding agents: agent CLIs run side by side as cards, each with a live terminal, and you wire
them to browsers, terminals, notes and each other with arrows. Windows 10 and 11, 64-bit.

## Install

```powershell
scoop bucket add neurosquad https://github.com/glmn-ai/scoop-neurosquad
scoop install neurosquad
```

NeuroSquad then is in the Start menu. It needs a free NeuroSquad account (the app asks you to sign
in on first launch).

## How it installs

The manifest runs NeuroSquad's own installer unattended
(`NeuroSquad-Setup.exe --silent --no-desktop --dir <scoop app dir>\app`), downloaded from the
[official releases](https://github.com/glmn-ai/neurosquad-releases/releases) and checked against
its SHA-256. The installer adds the Start menu shortcut (Windows notifications need it) and an
entry in Apps & features; `scoop uninstall neurosquad` runs NeuroSquad's uninstaller, which removes
exactly what was installed. Your data in `%APPDATA%\NeuroSquad` stays.

NeuroSquad updates itself; `scoop update neurosquad` works too. The manifest follows new releases
automatically ([Excavator](.github/workflows/excavator.yml), `checkver` + `autoupdate`).

## Other ways to install

- The download page: <https://neurosquad.ai/download>
- winget: `winget install NeuroSquad.NeuroSquad`
- PowerShell: `irm https://neurosquad.ai/install.ps1 | iex`
