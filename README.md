# sescontrol
*one-liner sed commands to turn the KDE Screen Energy Saving setting on or off*

KDE Plasma sometimes overrides application requests to keep the screens on.
This can be a hassle to deal with when using multimedia or gaming applications.
These scripts are one-liner `sed` commands that control the SES setting config.

Plasma's energy settings are generally stored in `$HOME/.config/powermanagementprofilesrc`.
If the sed command in `ses-off` finds them, it will comment out the following lines:

```
[AC][DPMSControl]
idleTime=600
```

Conversely, `ses-on` will uncomment those lines if they are found commented.

The effect of this will be to turn the Screen Energy Saving setting on or off
in `System Settings > Hardware > Power Management > On AC Power`.

You can use these as pre-launch and post-exit for multimedia applications like
VNC, gaming applications like Lutris, and anything else that requires constant
uninterrupted screen usage in KDE.

The sed command used in these scripts was adapted from a
[StackOverflow answer](https://stackoverflow.com/a/30646076/4648080) from user
nu11p01n73R.