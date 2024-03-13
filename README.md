
# HyprDots

![GitHub last commit](https://img.shields.io/github/last-commit/markpendlebury/HyprDots) ![Static Badge](https://img.shields.io/badge/Prs-Welcome-blue)


A fully repeatable desktop environment built on Arch using Hyprland

Welcome! My goal with this repository was to provide myself with a personal development desktop environment that is repeatable and managed by source control. This allows me to make changes, test them, throw them away and move them to a new machine / fresh install with minimal post-setup.

# Screenshots

![Empty Desktop Screenshot](https://github.com/markpendlebury/HyprDots/blob/initial/Assets/desktop.png)

![Application Screenshot](https://github.com/markpendlebury/HyprDots/blob/initial/Assets/apps.png)

# Features

- Hyprland - nuff said...
- Full Autotiling and keyboard navigation
- Fully automated installation
- Version controlled dotfiles
- Fully pallet matched desktop environment
 

# Installation

I strongly recommend you build this into a clean minimal installation of Arch. During your clean installation of Arch be sure to add git as an additional package, then once installation has complete and you've logged into for the first time, simply clone this repo, cd into it and run `./setup.sh`. Once complete reboot and you'll find yourself at the SDDM Login Screen. 

1. Fork this repository
2. Install a minimal installation of Arch Linux 
    a. Be sure to install git as an additional package
3. After installation completes, clone your forked version of this repo
4. cd into the directory and run `./setup.sh`
5. Reboot

# Usage
Generally if I want to add a new tool or feature to my environment I'll start by creating a branch from main. Then I'll manually install the applications / tools or make whatever changes I want to then add it to the installation list inside `setup.sh`. If it's an application install and I want to maintain the configs I'll move them under `Dotfiles/` and create a `ln` line for them inside `setup.sh`. Once I'm happy with my changes I'll push my branch and merge into main.

# Navigation
I hardly use my mouse, only for things I really have to like interacting with firefox or other UI's that don't like keyboard shortcuts. For that reason my hyprland config is almost entirely designed around the following keyboad shortcuts:

Bindings are as follows: 
`$mainMod = Super`
`$mainAlt = Left Alt`
`$mainCtrl = Left Ctrl`

**Application Shortcuts** 
| Shortcut | Action |
|--|--|
| $mainMod + Return | Open Terminal |
| $mainMod + E | Open Thunar | 
| $mainMod + B | Open Firefox | 
| $mainMod + V | Open Code | 
| $mainMod + L | Lock Screen | 
| $mainMod + SPACE | Open Wofi / App launcher | 
| $mainMod + J | Toggle window split |
| $mainMod + Q | Quit current focused app/window | 

**Navigation Shortcuts**

| Shortcut | Action |
| -- | -- |
| $mainMod + LEFT | Focus left window | 
| $mainMod + RIGHT | Focus right window | 
| $mainMod + UP | Focus upper window | 
| $mainMod + DOWN | Focus lower window |
| $mainMod + # | Move to workspace # |  
| $mainMod + SHIFT + # | Move current window to workspace # |  
| $mainMod + WHEEL_UP | Move to next workspace |  
| $mainMod + WHEEL_Down | Move to previous workspace |
| $mainMod + MOUSE_LEFT | Drags the selected window |  
| $mainMod + MOUSE_RIGHT | Resize the selected window |


# Notes
As it currently stands, setup.sh is designed to be used on a fresh installation of Arch, whilst it is technically possible to use it to "keep your env in sync" so to speak - I haven't fully tested it yet. Ideally I'd like it to function in a similar way to how nix works where `setup.sh` runs priodically to keep my system in sync. Or maybe I'll just switch to nixos as somepoint....

  
# Core Components:

| Compositor: [Hyprland](https://hyprland.org/) | Bar: [Waybar](https://github.com/Alexays/Waybar) | Application Launcher: [Wofi](https://hg.sr.ht/~scoopta/wofi) |
| :-: | :-: | :-: |
| **Login**: [SDDM](https://github.com/sddm/sddm) | **Notifications**: [Mako](https://github.com/emersion/mako) | **File Manager**: [Thunar](https://docs.xfce.org/xfce/thunar/start) |
| **Terminal**: [Kitty](https://github.com/kovidgoyal/kitty) | **Walls**: [swww](https://github.com/LGFae/swww) | **Lock**: [Swaylock](https://github.com/swaywm/swaylock) |

# Color Pallet

Currently everything is themed according to (or based off of) enkia's Tokyo Night Storm [VSCode](https://github.com/enkia/tokyo-night-vscode-theme) color pallet (or just Tokyo Night where storm wasn't possible) I do plan in future switching over to GruvBox or maybe even building some kind of switcher, initially probably just a branch based theme selector.

| Color&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Use |
| ---------- | ------------------------------------------------------------ |
| ![#f7768e](https://place-hold.it/15/f7768e/f7768e?text=+) `#f7768e` | This keyword, HTML elements, Regex group symbol, CSS units, Terminal Red |
| ![#ff9e64](https://place-hold.it/15/ff9e64/ff9e64?text=+) `#ff9e64` | Number and Boolean constants, Language support constants |
| ![#e0af68](https://place-hold.it/15/e0af68/e0af68?text=+) `#e0af68` | Function parameters, Regex character sets, Terminal Yellow |
| ![#9ece6a](https://place-hold.it/15/9ece6a/9ece6a?text=+) `#9ece6a` | Strings, CSS class names |
| ![#73daca](https://place-hold.it/15/73daca/73daca?text=+) `#73daca` | Object literal keys, Markdown links, Terminal Green |
| ![#b4f9f8](https://place-hold.it/15/b4f9f8/b4f9f8?text=+) `#b4f9f8` | Regex literal strings |
| ![#2ac3de](https://place-hold.it/15/2ac3de/2ac3de?text=+) `#2ac3de` | Language support functions, CSS HTML elements |
| ![#7dcfff](https://place-hold.it/15/7dcfff/7dcfff?text=+) `#7dcfff` | Object properties, Regex quantifiers and flags, Markdown headings, Terminal Cyan, Markdown code, Import/export keywords |
| ![#7aa2f7](https://place-hold.it/15/7aa2f7/7aa2f7?text=+) `#7aa2f7` | Function names, CSS property names, Terminal Blue |
| ![#bb9af7](https://place-hold.it/15/bb9af7/bb9af7?text=+) `#bb9af7` | Control Keywords, Storage Types, Regex symbols and operators, HTML Attributes, Terminal Magenta |
| ![#c0caf5](https://place-hold.it/15/c0caf5/c0caf5?text=+) `#c0caf5` | Variables, Class names, Terminal White |
| ![#a9b1d6](https://place-hold.it/15/a9b1d6/a9b1d6?text=+) `#a9b1d6` | Editor Foreground |
| ![#9aa5ce](https://place-hold.it/15/9aa5ce/9aa5ce?text=+) `#9aa5ce` | Markdown Text, HTML Text |
| ![#cfc9c2](https://place-hold.it/15/cfc9c2/cfc9c2?text=+) `#cfc9c2` | Parameters inside functions (semantic highlighting only) |
| ![#565f89](https://place-hold.it/15/565f89/565f89?text=+) `#565f89` | Comments |
| ![#414868](https://place-hold.it/15/414868/414868?text=+) `#414868` | Terminal Black |
| ![#24283b](https://place-hold.it/15/24283b/24283b?text=+) `#24283b` | Editor Background (Storm) |
| ![#1a1b26](https://place-hold.it/15/1a1b26/1a1b26?text=+) `#1a1b26` | Editor Background (Night) |
  
# Included Packages

When using `setup.sh` the following applications will be installed. It's possible to remove/add any application you like (see below) during installation, but once they're installed you'll have to use yay (`yay -R {application name}`) to remove them

| Core | Application | CLI |
| :-------------------------: | :-------------------: | :-----------: |
| llinux-headers | Kitty | git |
| QT5-Wayland | Swappy | JQ |
| QT5CT | Grim | OpenSSH |
| Hyprland | Slurp | GVFS |
| Mako | Thunar | File Roller |
| SWW | Thunar-Archive-Plugin | Btop |
| Sway | OBS-Studio | Tree |
| Swaylock | Firefox | rTorrent |
| Swaylock-Effects | Visual Studio Code | Neofetch |
| Swayidle | | Bitwarden-Cli |
| Wofi | | Wget |
| xdg-desktop-portal-hyprland | | Zsh |
| Polkit-Gnome | | Nano |
| Python-Requests | | aws-cli-v1 |
| PA Mixer | | Vault |
| PAVUControl | | |
| Bluez | | |
| Bluez-Utils | | |
| Blueman | | |
| Network-Manager Applet | | |
| Network-Manager OpenVPN | | |
| Pacman-Contrib | | |
| LX-Apperance | | |
| XFCE4-Settings | | |
| SDDM | | |
| QT5-SVG | | |
| QT5-Quickcontrols2 | | |
| QT5-GraphicalEffects | | |

# Dotfiles
All dots are located under [Dotfiles/](https://github.com/markpendlebury/HyprDots/tree/main/Dotfiles). I recommend you leave them in this location and rely on the [symlink](https://github.com/markpendlebury/HyprDots/blob/main/setup.sh#L189)  stage of [setup.sh](https://github.com/markpendlebury/HyprDots/blob/main/setup.sh) to link them into the correct locations. You can however move pick and chose which dots you want, if that's the case I'm going to assume you know what you're doing.