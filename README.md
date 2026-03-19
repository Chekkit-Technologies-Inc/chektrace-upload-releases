![Alt text for the image](https://storage.googleapis.com/chektrace-public-assets/Chektrace-Full-Logo.png)

# Chektrace Upload — Releases

This repository contains auto-update artifacts for the **Chektrace Upload** desktop app.

> **Do not modify this repository manually.**
> All releases are created automatically by the CI/CD pipeline in the source repository.
> Manually editing or deleting releases will break the in-app auto-updater for all users.

## Contents

Each release contains:

| File | Description |
|------|-------------|
| `latest.json` | Update manifest consumed by the Tauri in-app updater |
| `*.app.tar.gz` | macOS update bundle |
| `*.app.tar.gz.sig` | Cryptographic signature for the macOS bundle |
| `*.exe.sig` | Cryptographic signature for the Windows installer |
| `*.msi.sig` | Cryptographic signature for the Windows MSI |

## How it works

1. A release is triggered by pushing a version tag to the private source repo
2. The CI builds macOS (universal) and Windows (x64) installers
3. Once both builds finish, signed update artifacts and `latest.json` are published here
4. The Chektrace Upload app checks this repo's `latest` release on launch and when triggered from the OS menu

## Full installers

`.dmg` and `.exe` installers for fresh installs are distributed separately through internal channels — they are not hosted here.

## Source

Source code is maintained in a private repository. Contact the Chekkit Technologies team for access.
