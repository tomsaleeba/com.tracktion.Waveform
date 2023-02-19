Fork notes
---
This isn't published to anywhere yet, so you need to build it yourself.

Thanks to [alesya-h](https://github.com/alesya-h) for all the hard work on updating to
Waveform12.

The changes I made
- change package name to include `12`, so it's a separate app from v11, as suggested in
  [this comment](https://github.com/flathub/com.tracktion.Waveform/pull/7#issuecomment-1126780423)
- update to use the latest v12 available


## How to build
Building is basically following: https://docs.flatpak.org/en/latest/first-build.html

Clone this repo.

Make sure `flatpak-builder` is installed 
```
yay -S flatpak-builder
```

Install the platform SDK
```
flatpak install flathub org.freedesktop.Platform//21.08 org.freedesktop.Sdk//21.08
```

Build the project
```
flatpak-builder build-dir com.tracktion.Waveform12.yml
```

Install the built package
```
flatpak-builder --user --install --force-clean build-dir com.tracktion.Waveform12.yml
```

Run the app
```
flatpak run -u com.tracktion.Waveform12 
```


Flathub
-------

Flathub is the central place for building and hosting Flatpak builds.
Go to https://flathub.org/builds/ to see Flathub in action.

Building applications
---------------------

Application manifests should go in their own repository in the [Flathub](https://github.com/flathub) organization,
named after the application ID.

For example, for gnome-recipes, there is a repository named org.gnome.Recipes which has the org.gnome.Recipes.json
file at the toplevel.

Hosted builds should be stable releases, not development snapshots, so please use tarballs or git tags, not just
the tip of a branch.

More detailed requirements can be found in the [Review Guidelines](https://github.com/flathub/flathub/wiki/Review-Guidelines)

Using the Flathub repository
----------------------------

To install applications that are hosted on Flathub, use the following:
```
flatpak remote-add flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.gnome.Recipes
```
