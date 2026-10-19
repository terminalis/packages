# Terminalis packages

Signed package repositories for apps by terminalis.

## Install

Envarsa:

```sh
flatpak install --user https://terminalis.github.io/packages/flatpak/envarsa.flatpakref
```

Gittin:

```sh
flatpak install --user https://terminalis.github.io/packages/flatpak/gittin.flatpakref
```

New versions then arrive through `flatpak update` and software centers such as GNOME Software and KDE Discover.

To add the Flatpak repository without installing an app, so software centers list every app in it:

```sh
flatpak remote-add --user --if-not-exists terminalis https://terminalis.github.io/packages/flatpak/terminalis.flatpakrepo
```

The apps use runtimes from Flathub, so that needs the Flathub remote too. An app's `.flatpakref` adds it by
itself.

## How it works

Each folder here is a package format. After each app's release, `.github/workflows/publish.yml` builds the
signed repositories from the apps' latest GitHub Releases and publishes each package format at
`https://terminalis.github.io/packages/<folder>`.
