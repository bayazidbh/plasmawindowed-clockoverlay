# plasmawindowed-clockoverlay
Run Digital Clock as a Clock Overlay for KDE Plasma

<details><summary>View Screenshot:</summary><p>

![image](https://github.com/user-attachments/assets/f8687ee4-d284-474b-9f5b-5ad11afc4670)

</p></details>

<details><summary>Fullscreen in-game:</summary><p>
  
![image](https://github.com/user-attachments/assets/55ac117f-9aae-4460-bb9d-ca1cfb5ec045)

</p></details>

## Install:

Click **Code** > **Download zip**, then extract the file.

Copy `plasmawindowed-clockoverlay.desktop` to `/home/$USER/.config/autostart/` (to run at Desktop Mode / KDE Plasma startup), `/home/$USER/.local/share/applications/` (for App Launcher/Start Menu), or  `/home/$USER/Desktop` (for Desktop access). Double click it to run immediatelly (or copy-paste the Exec command to terminal).

(If you want to change to 24-hours, do it now -- click it and open its setting -- as it has its own setting separate from any existing clock widgets)

Open System Settings, and search for `rules` which should show Window Rules under Apps & Windows > Window Management. Click Import and open `clockoverlay.kwinrule`.

<details><summary>Show Image</summary><p>

![image](https://github.com/user-attachments/assets/6b342f8d-2be5-4621-a54d-15fb34e345c2)

</p></details>

(Alternatively, you can manually copy paste it to `/home/$USER/.config/kwinrulesrc` or you can manually configure the window rules yourself using Detect Window Property in that setting menu.)

<details><summary>Show Image</summary><p>

![image](https://github.com/user-attachments/assets/dbdcca73-af40-48c9-8b6d-59c0a6cf8ac8)

</p></details>

Edit the settings as needed, such as whether it skips pager (Overview) and if it is Closeable. I don't recommend disabling Accept Focus - I couldn't find a way to reject click/touch inputs and dismissing the calendar menu can be annoying with it). The window position is set to Remember so you can use Meta + Click and Drag to move it to a more convenient position.

<details><summary>Show Image</summary><p>

![image](https://github.com/user-attachments/assets/ecdc325d-6184-4d25-9dcd-fce6131790a5)

</p></details>

## Manual Install

If you rather copy paste the files, here are the contents:

<details><summary>Expand</summary><p>

- plasmawindowed-clockoverlay.desktop:
```
[Desktop Entry]
Comment[en_US]=
Comment=
Exec=plasmawindowed org.kde.plasma.digitalclock '>' /dev/null '2>&1'
GenericName[en_US]=
GenericName=
Icon=
MimeType=
Name[en_US]=plasmawindowed
Name=plasmawindowed
Path=
StartupNotify=true
Terminal=false
TerminalOptions=
Type=Application
X-KDE-SubstituteUID=false
X-KDE-Username=
```

- clockoverlay.kwinrule:

```
[Window settings for Digital Clock]
Description=Window settings for Digital Clock
above=true
aboverule=2
acceptfocusrule=1
closeablerule=2
desktops=\\0
desktopsrule=2
ignoregeometry=true
ignoregeometryrule=2
layer=overlay
layerrule=2
noborder=true
noborderrule=2
opacityactive=30
opacityactiverule=2
opacityinactive=30
opacityinactiverule=2
position=1421,82
positionrule=4
size=70,99
sizerule=2
skippager=true
skippagerrule=2
skipswitcher=true
skipswitcherrule=2
skiptaskbar=true
skiptaskbarrule=2
title=Digital Clock
wmclass=plasmawindowed org.kde.plasmawindowed
wmclasscomplete=true
wmclassmatch=1
```

</p></details>

## Motivation

"This is just a configuration of built-in KDE Plasma applets, anyone can do it themself."

Yes, but when I was looking up for a clock overlay, the closest thing I could find was someone mentioning you can use plasmawindowed to run Digital Clock applet on its own window in a Manjaro Forum post.

No one's made a quick "ready-to-install" or "just copy-paste" thing yet so I decided to just post my 'config' to github both for personal backup and so anyone else who googled clock overlay for Steam Deck Desktop Mode or KDE Plasma in general could find it, download it, and quickly install it (also, I don't like people assuming others _already_ know the basics about Linux with their instructions).

And yes, I have a clock on my top panel. It's really not enough when you're fullscreen deep in a strategy game in Desktop Mode and you've already dismissed all your time-to-sleep alarms. I just want yet another clock, just in case, to remind me what time it is right now and because why the heck not.

## Credits and Links

- Thanks to [tuxmanjarino at Manjaro Forum](https://forum.manjaro.org/t/how-do-i-make-a-widget-be-on-top-of-everthing/57562) for informing about `plasmawindowed`.
- Thanks to [/u/Human-Equivalent-154](https://www.reddit.com/user/Human-Equivalent-154) and [/u/imhitchens](https://www.reddit.com/user/imhitchens) (and whoever the original commenter was) for telling about [Layer > Overlay window rule](https://www.reddit.com/r/kde/comments/z0zptp/is_it_possible_to_keep_a_window_above_a_full/mklebqh/).
- KDE Plasma for being KDE Plasma.
