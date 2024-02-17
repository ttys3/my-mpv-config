
https://github.com/tomasklaen/uosc

https://iamscum.wordpress.com/guides/videoplayback-guide/mpv-conf/

https://github.com/marzzzello/mpv_thumbnail_script

https://mpv.io/manual/master/#keyboard-control

https://github.com/hooke007/MPV_lazy

https://github.com/hooke007/MPV_lazy/discussions/61

## subtitle

```shell
❯ mpv --list-properties | rg secondary
 secondary-sid
 secondary-sub-text
 secondary-sub-start
 secondary-sub-end
 secondary-sub-visibility
```

https://github.com/mpv-player/mpv/issues/10938

## troubleshoot

https://mpv.io/manual/master/#disabling-screensaver

By default, mpv tries to disable the OS screensaver during playback (only if a VO using the OS GUI API is active). --stop-screensaver=no disables this.

A common problem is that Linux desktop environments ignore the standard screensaver APIs on which mpv relies. In particular, mpv uses the Screen Saver extension (XSS) on X11, and the idle-inhibit protocol on Wayland.

GNOME in particular still ignores the idle-inhibit protocol, and has its own D-Bus interfaces for display power management, which mpv does not support.

Before mpv 0.33.0, the X11 backend ran xdg-screensaver reset in 10 second intervals when not paused in order to support screensaver inhibition in these environments. This functionality was removed in 0.33.0, but it is possible to call the xdg-screensaver command line program from a user script instead.


https://mpv.io/manual/master/#options-secondary-sid

There are some caveats associated with this feature.
For example, bitmap subtitles will always be rendered in their usual position,
so selecting a bitmap subtitle as secondary subtitle will result in overlapping subtitles.
Secondary subtitles are never shown on the terminal if video is disabled.


Note

If the main subtitle stream contains formatting tags which display the subtitle at the top of the screen, it will overlap with the secondary subtitle.
To prevent this, you could use --no-sub-ass to disable styling in the main subtitle stream.

## refs

https://wiki.archlinux.org/title/mpv#Key_bindings
