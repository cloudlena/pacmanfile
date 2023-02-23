# Pacmanfile

[![pacmanfile](https://img.shields.io/aur/version/pacmanfile?color=1793d1&label=pacmanfile&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/pacmanfile/)

Pacmanfile is a tool that allows to declaratively define which packages you want to have installed via Arch Linux' [Pacman](https://wiki.archlinux.org/index.php/Pacman), [Yay](https://aur.archlinux.org/packages/yay/) or [Paru](https://github.com/morganamilo/paru) to include packages from the [AUR](https://aur.archlinux.org/).

## Installation

Pacmanfile is available in the [AUR](https://aur.archlinux.org/packages/pacmanfile/).

1. Run `paru -S pacmanfile`

## Usage

1. Run `pacmanfile help` to get an overview of the existing commands and flags.

1. Run `pacmanfile dump` which dumps your currently explicitly installed packages into a pacmanfile.

   Alternatively, you can manually create a `pacmanfile.txt` file in your `$XDG_CONFIG_HOME/pacmanfile` directory (usually `~/.config/pacmanfile`) which contains all the packages you want to have installed. Here's an example:

   ```txt
   alacritty
   base
   git
   linux
   linux-firmware
   zsh
   ```

   You can split the file up into any number of files that match `pacmanfile*.txt` (e.g. `pacmanfile-extra.txt`).

   You can add comments to pacmanfiles by starting any line with a `#`.

1. Run `pacmanfile sync`. This will remove any packages that you have installed which are not listed in `pacmanfile*.txt` and install any packages that you have not yet installed but that are listed in `pacmanfile*.txt`.

## Limitations

Pacmanfile expects its packages to be installed explicitly. In case it complains about a package not being installed, you need to change that package's installation reason to explicit by running `sudo pacman -D --asexplicit PACKAGE_NAME`.

Currently, installing groups with `pacmanfile` is not supported. The workaround is to list all the members of the group individually in your file.
