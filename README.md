# Terminalis Flatpak repository

A signed Flatpak repository for apps by terminalis, at `https://terminalis.github.io/flatpak/repo`.

## Install

Envarsa:

```sh
flatpak install --user https://terminalis.github.io/flatpak/envarsa.flatpakref
```

New versions then arrive through `flatpak update` and software centers such as GNOME Software and KDE Discover.

## How it works

`.github/workflows/publish.yml` downloads the newest `*_x86_64.flatpak` from each app's latest GitHub Release,
imports it into an empty repository, signs it, and deploys `site/` to GitHub Pages. It runs after each app's
release.
