# Lunch and learn - NIX

### 1. Download and install NIX on your system

Visit the [NIX installation page](https://nixos.org/download.html) and follow the instructions for your operating system.

### 2. Setup NIX unstable channel

```bash
nix-channel --add https://nixos.org/channels/nixpkgs-unstable nixpkgs
nix-channel --update
```

This command adds the NIX unstable channel to your NIX configuration and updates the package list.

### 3. Setup your first nix shell environment

Create a default.nix file in your project directory with the following content:

```nix
{ pkgs ? import <nixpkgs> {} }:

pkgs.mkShell {
  buildInputs = [

  ];
}
```

### 4. Install the dependencies of your choice

Visit nix packages website [nixpkgs](https://search.nixos.org/packages) and search for the packages you want to install. For example, if you want to install Python 3.9 and pip, you can add them to the `buildInputs` list:

```nix
{ pkgs ? import <nixpkgs> {} }:
pkgs.mkShell {
  buildInputs = [
    pkgs.python39
    pkgs.python39Packages.pip
  ];
}
```

### 5. Enter the nix shell

```bash
nix-shell
```

This will create a virtual environment with Python 3.9 and pip installed.

## Advanced usage

[TODO]
