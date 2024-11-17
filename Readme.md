# Dconf editor in gui mode:
org > mate > desktop > session > required-components. Change windowmanager from marco to i3.

org > mate > desktop > session and in required-component-list, delete filemanager. 

org > mate > desktop >background>show-desktop-icons to false

# Via Commandline:

- dconf write /org/mate/desktop/session/required-components/windowmanager "'i3'"
- dconf write /org/mate/desktop/background/show-desktop-icons false


# Fixing i3 borders

Add "for_window [window_type="normal"] border normal" to your i3 config(~/.config/i3/config):
Press SUPER+SHIFT+R

# Fixing montior name  pop up
mate desktop monitor name stuck popup

# Fixing lingering montior number
lingering "mate-display-properties" processes running. Killing all of them fixed the issue.

# Making fonts sharper

export FREETYPE_PROPERTIES="cff:no-stem-darkening=0 autofitter:no-stem-darkening=0"

First, to find your screen's actual DPI:
xrandr | grep -w connected

Find your screen resolution and size:
This will show something like "1920x1080+0+0" and might show the physical size in millimeters.

Or for more detailed info:
xdpyinfo | grep dimensions

To calculate DPI manually, you need:

Your screen resolution (e.g., 1920x1080)

Your screen's physical size in inches (measure diagonally)



The formula is:
DPI = sqrt(width_in_pixels² + height_in_pixels²) / diagonal_inches


For example, for a 24-inch 1920x1080 monitor:
DPI = sqrt(1920² + 1080²) / 24 ≈ 92
For mine its  /27 which is 81.589


To set the DPI in MATE:
sudo apt install dconf-editor
dconf-editor
Then navigate to: org → mate → desktop → font-rendering → dpi

Method 2 - Using gsettings:

gsettings set org.mate.desktop.font-rendering dpi YOUR_DPI


# References:

- https://ubuntu-mate.community/t/how-to-install-i3wm-mate/26763
- https://mattgreer.dev/blog/mate-and-i3/
