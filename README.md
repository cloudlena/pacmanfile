# Pacmanfile

Pacmanfile is a tool that allows to declaratively define which packages you want to have installed via Arch Linux' [Pacman](https://wiki.archlinux.org/index.php/Pacman) or [Yay](https://aur.archlinux.org/packages/yay/) to include packages from the [AUR](https://aur.archlinux.org/).

## Installation

Pacmanfile is available in the [AUR](https://aur.archlinux.org/packages/pacmanfile/).

1. Run `yay -S pacmanfile`

## Usage

1. Create a `pacmanfile.txt` file in your `$XDG_CONFIG_HOME/pacmanfile` directory (usually `~/.config/pacmanfile`) which contains all the packages you want to have installed. Here's an example:

   ```txt
   alacritty
   base
   git
   linux
   linux-firmware
   zsh
   ```

   You can split the file up into any number of files that match `pacmanfile*.txt` (e.g. `pacmanfile.extra.txt`).

   A good way to start is to use the `pacmanfile dump` command which dumps your currently explicitly installed packages into a pacmanfile.

1. Run `pacmanfile sync`. This will remove any packages that you have installed which are not listed in `pacmanfile.txt` and install any packages that you have not yet installed but that are listed in `pacmanfile.txt`.
