# HyprDots

A fully repeatable desktop environment built on Arch using Hyprland

Welcome! My goal with this repository was to provide myself with a personal development that is repeatable and managed by source control. This allows me to make changes, test them, throw them away and move them to a new machine / fresh install with minimal post-setup.

# Screenshots

![Empty Desktop Screenshot](https://github.com/markpendlebury/HyprDots/blob/initial/Assets/desktop.png)

![Application Screenshot](https://github.com/markpendlebury/HyprDots/blob/initial/Assets/apps.png)

# Core Components:

|        Compositor: [Hyprland](https://hyprland.org/)       |       Bar: [Waybar](https://github.com/Alexays/Waybar)      |     Application Launcher: [Wofi](https://hg.sr.ht/~scoopta/wofi)    |
| :--------------------------------------------------------: | :---------------------------------------------------------: | :-----------------------------------------------------------------: |
|       **Login**: [SDDM](https://github.com/sddm/sddm)      | **Notifications**: [Mako](https://github.com/emersion/mako) | **File Manager**: [Thunar](https://docs.xfce.org/xfce/thunar/start) |
| **Terminal**: [Kitty](https://github.com/kovidgoyal/kitty) |       **Walls**: [swww](https://github.com/LGFae/swww)      |       **Lock**: [Swaylock](https://github.com/swaywm/swaylock)      |

# Themes

Currently everything is themed according to Tokyo Night Storm (or just Tokyo Night where storm wasn't possible) I do plan in future switching over to GruvBox or maybe even building some kind of switcher, initially probably just a branch based theme selector.

# Included Packages

When using `setup.sh` the following applications will be installed. It's possible to remove/add any application you like (see below) during installation, but once they're installed you'll have to use yay (`yay -R {application name}`) to remove them

|             Core            |      Application      |      CLI      |
| :-------------------------: | :-------------------: | :-----------: |
|        llinux-headers       |         Kitty         |      git      |
|         QT5-Wayland         |         Swappy        |       JQ      |
|            QT5CT            |          Grim         |    OpenSSH    |
|           Hyprland          |         Slurp         |      GVFS     |
|             Mako            |         Thunar        |  File Roller  |
|             SWW             | Thunar-Archive-Plugin |      Btop     |
|             Sway            |       OBS-Studio      |      Tree     |
|           Swaylock          |        Firefox        |    rTorrent   |
|       Swaylock-Effects      |   Visual Studio Code  |    Neofetch   |
|           Swayidle          |                       | Bitwarden-Cli |
|             Wofi            |                       |      Wget     |
| xdg-desktop-portal-hyprland |                       |      Zsh      |
|         Polkit-Gnome        |                       |      Nano     |
|       Python-Requests       |                       |   aws-cli-v1  |
|           PA Mixer          |                       |     Vault     |
|         PAVUControl         |                       |               |
|            Bluez            |                       |               |
|         Bluez-Utils         |                       |               |
|           Blueman           |                       |               |
|    Network-Manager Applet   |                       |               |
|   Network-Manager OpenVPN   |                       |               |
|        Pacman-Contrib       |                       |               |
|         LX-Apperance        |                       |               |
|        XFCE4-Settings       |                       |               |
|             SDDM            |                       |               |
|           QT5-SVG           |                       |               |
|      QT5-Quickcontrols2     |                       |               |
|     QT5-GraphicalEffects    |                       |               |
|                             |                       |               |

