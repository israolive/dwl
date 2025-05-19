# dwl - dwm for Wayland

This is my fork of [DWL](https://codeberg.org/dwl/dwl). Inspired by [https://github.com/julmajustus/dwl-deep-dive](https://github.com/julmajustus/dwl-deep-dive).

## Dependencies


```sh
sudo pacman -S libinput wayland wlroots libxkbcommon wayland-protocols pkg-config
```

Also for XWayland support

```sh
sudo pacman -S libxcb xorg-xwayland
```

## Build

### Enable XWayland support

Edit `config.mk` and uncomment the following lines:

```bash
#XWAYLAND = -DXWAYLAND
#XLIBS = xcb xcb-icccm
```

```
make

sudo make install
```

## Patches

- [btrtile](https://codeberg.org/dwl/dwl-patches/src/branch/main/patches/btrtile)  
    A tiling layout that gives the user more control over tiled clients, with full support for managing clients via both keyboard and mouse.

- [focusdir](https://codeberg.org/dwl/dwl-patches/src/branch/main/patches/focusdir)  
    Enables moving focus between clients.

- [rotatetags](https://codeberg.org/dwl/dwl-patches/src/branch/main/patches/rotatetags)  
    Allows you to rotate the view or shift clients between tags.

- [warpcursor](https://codeberg.org/dwl/dwl-patches/src/branch/main/patches/warpcursor)  
    Moves the cursor to the focused client.

- [pertag](https://codeberg.org/dwl/dwl-patches/src/branch/main/patches/pertag)  
    Allows each tag to have individual tiling layout setups.

- [gaps](https://codeberg.org/dwl/dwl-patches/src/branch/main/patches/gaps)  
    Adds gaps between clients and screen edges for a cleaner look.

- [ipc](https://codeberg.org/dwl/dwl-patches/src/branch/main/patches/ipc)  
    IPC-protocol for dwl, we need it later for our waybar (taskbar).

### How to

```
git am -3 path/to/myfeature.path

git apply path/to/myfeature.patch

patch -p1 < path/to/myfeature.patch 
```

```
make clean all
```
