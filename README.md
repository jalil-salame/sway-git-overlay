# Sway git overlay

> [!Warning]
> This repo is unmantained, you should instead use
> [nixpkgs-wayland](https://github.com/nix-community/nixpkgs-wayland)

An overlay for `nix` that adds `sway`'s git version to your packages.

## Usage

Add this overlay to your flake inputs:

```nix
inputs.sway-git-overlay.url = "github:jalil-salame/sway-git-overlay";
```

Then apply it to your packages:

```nix
let
  overlays = [
    sway-git-overlay.overlays.default # provides sway-git
    # sway-git-overlay.overlays.replace-sway # replaces sway with sway-git (anywhere you use pkgs.sway you'll get pkgs.sway-git instead)
  ];
  pkgs = import nixpkgs { inherit system overlays;};
in ...
```

You can also test the package directly with:

```console
$ nix run github:jalil-salame/sway-git-overlay
```
