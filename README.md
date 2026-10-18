# Terminalis packages

Signed package repositories for apps by terminalis, served from `https://terminalis.github.io/packages/`. For
now that's a Flatpak repository, at `https://terminalis.github.io/packages/flatpak`.

## Install

Envarsa:

```sh
flatpak install --user https://terminalis.github.io/packages/envarsa.flatpakref
```

New versions then arrive through `flatpak update` and software centers such as GNOME Software and KDE Discover.

To add the repository without installing an app, so software centers list every app in it:

```sh
flatpak remote-add --user --if-not-exists terminalis https://terminalis.github.io/packages/terminalis.flatpakrepo
```

The apps use runtimes from Flathub, so that needs the Flathub remote too. An app's `.flatpakref` adds it by
itself.

## How it works

`.github/workflows/publish.yml` downloads the newest `*_x86_64.flatpak` from each app's latest GitHub Release,
imports it into an empty repository, signs it, and deploys `site/` to GitHub Pages. It runs after each app's
release.
