# bug-keyboard-layout

This is a custom keyboard layout heavily inspired by [the Bépo layout](https://bepo.fr/wiki/Accueil).
The point of this project is to have a confortable keyboard layout based on my personal day-to-day use. Also because curiosity.


# Windows
## Installation
Simply pull the project and launch the `windows/prebuild/setup.exe` file.
Then restart your computer and voilà.

## Removal
You can uninstall the layout like any program by going into your Windows settings in 'Apps & features'.

## Edition
If you want to change anything you can load the `windows/bug.klc` file in [Microsoft keyboard layout creator](https://www.microsoft.com/en-us/download/details.aspx?id=102134).

Once done it will generate the necessary files along with a setup.exe that you can use. Remember that you will need to uninstall the bug layout before if you wish to keep the name.



# Linux (at least Ubuntu)
## Installation
Pick the language you want the layout to be configured as. I chose 'us' because I was using international qwerty before but 'fr' makes more sense here.


Backup `/usr/share/X11/xkb/symbols/<language>` and `/usr/share/X11/xkb/rules/evdev.xml` anywhere you want, just in case.


Copy the content of `linux/symbols` at the end of the `/usr/share/X11/xkb/symbols/<language>` of your choice.


After that you need to copy the content of `linux/variant` into `/usr/share/X11/xkb/rules/evdev.xml`. I recommend putting it right after whatever keyboard you are using now but the important part is to put it into the '<variantList>' of the language you chose before. So for me it was right after the 'English (US, intl., with dead keys)' variant.

(Optional) You may also want to add this keyboard as the default in `/etc/default/keyboard` by setting the 'XKBLAYOUT' to your chosen language and 'XKBVARIANT' to 'bug'.
But it may be wise to do that once you are sure everything works.

Restart your computer and you are good. If you did not change your default keyboard then you will need to use your previous layout to enter your pin. Then you will be able to swap to the new layout.

## Removal
Delete the lines you added during Installation.

## Edition
Edit your symbols in `/usr/share/X11/xkb/symbols/us` and reload your layout using `setxkbmap us bug`.
I recommend keeping your previous layout in your installed layouts to be able to swap back to it with your mouse if by chance you messed up something
