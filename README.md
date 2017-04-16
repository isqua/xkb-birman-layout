# XKB Typography Layout (us, ru)

This is xkb layout with accents and some useful symbols like this: ≈ © ® × ‰ and others.
It is based on [Ilya Birman typography layout](http://ilyabirman.net/projects/typography-layout/) v3.4.1 for mac OS.

Installation:

```bash
# clone this repo (or just download it)
git clone git@github.com:isqua/xkb-birman-layout.git
cd xkb-birman-layout

# Create directory for your own layouts
mkdir -p ~/.config/xkb/symbols/

# Put this layout to your home directory
cp home/config/xkb/symbols/* ~/.config/xkb/symbols/

# Add this XCompose settings to your XCompose
cat home/XCompose >> ~/.XCompose

# You may remove the repo:
cd ..
rm -r xkb-birman-layout
```

Then for using this layout you should execute this command at start of your x session (e.x. in `~/.xinitrc`).

```
setxkbmap "birman-us,birman-ru" "birman,birman" "grp:caps_toggle,grp:ralt_switch" -print | xkbcomp -I${HOME}/.config/xkb - $DISPLAY
```

`grp:caps_toggle,grp:ralt_switch` means switch layouts by press caps, and switch layer by right alt. You may set up other keys.

XCompose file is needed to remap double dead acute to combining acute. After change XCompose file you have to restart X server.
