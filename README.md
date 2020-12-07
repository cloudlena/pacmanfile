# Pacfile

Pacfile is a tool that allows to declaratively define which packages you want to have installed via Arch Linux' [Pacman](https://wiki.archlinux.org/index.php/Pacman) or [Yay](https://aur.archlinux.org/packages/yay/) to include packages from the [AUR](https://aur.archlinux.org/).

## Installation

Pacfile is available in the [AUR](https://aur.archlinux.org/packages/pacfile-bin/).

1. Run `yay -S pacfile-bin`

## Usage

1. Create a `pacfile.txt` file in your `$XDG_CONFIG_HOME/pacfile` directory (usually `~/.config/pacfile`) which contains all the packages you want to have installed. Here's an example:

   ```txt
   alacritty
   base
   git
   linux
   linux-firmware
   zsh
   ```

1. Run `pacfile sync`. This will remove any packages that you have installed which are not listed in `pacfile.txt` and install any packages that you have not yet installed but that are listed in `pacfile.txt`.
