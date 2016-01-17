Fix multimedia keys in i3
=========================

You can bind the following programs to the symbols to get the multimedia keys working in i3

```
# Pulse Audio controls
bindsym XF86AudioRaiseVolume exec --no-startup-id pactl set-sink-volume 1 +5% # increase sound volume
bindsym XF86AudioLowerVolume exec --no-startup-id pactl set-sink-volume 1 -5% # decrease sound volume
bindsym XF86AudioMute exec --no-startup-id pactl set-sink-mute 1 toggle # mute sound

# Sreen brightness controls
bindsym XF86MonBrightnessUp exec xbacklight -inc 20 # increase screen brightness
bindsym XF86MonBrightnessDown exec xbacklight -dec 20 # decrease screen brightness

# Media player controls
bindsym XF86AudioPlay exec playerctl play
bindsym XF86AudioPause exec playerctl pause
bindsym XF86AudioNext exec playerctl next
bindsym XF86AudioPrev exec playerctl previous
```

These must be included in the i3's configuration file.

Soure: https://faq.i3wm.org/question/3747/enabling-multimedia-keys.1.html

**Note about Pulse Audio controls**

The number `1` in the Pulse Audio controls section is the sink to be used. You can find the list of sinks with the following command
```
➜  i3 git:(master) pactl list short sinks
0       alsa_output.pci-0000_01_00.1.hdmi-stereo        module-alsa-card.c      s16le 2ch 44100Hz       SUSPENDED
1       alsa_output.pci-0000_00_1b.0.analog-stereo      module-alsa-card.c      s16le 2ch 44100Hz       RUNNING
```

The number corresponding to the `RUNNING` sink has to be provided there.
