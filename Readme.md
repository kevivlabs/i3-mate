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

solution
lingering "mate-display-properties" processes running. Killing all of them fixed the issue.
# References:

- https://ubuntu-mate.community/t/how-to-install-i3wm-mate/26763
- https://mattgreer.dev/blog/mate-and-i3/
