# Keywords

One of the Keck software infrastructure strengths is the keyword system.  All instrument functions should be controllable by keywords.  This creates a common interface layer for all instruments.  Under normal circumstances, SAs will not need to dive in to the details of the interface protocols for any given component of the instrument (e.g. serial interface, USB interface, etc.).

The two most basic actions one can perform with a keyword are `show` and `modify` which report the value of a keyword and change the value respectively.  Not all keywords can be modified and some can not show, and a number of the details vary across instruments, but in general, with these two tools one can create any higher level control interface ths is desires (e.g. a script or GUI).

Both `show` and `modify` need to be executed with an argument which specifies which service the keyword is in.  For example, if I wanted to find out how full the HIRES liquid nitrogen dewar is, I would query the `hiccd` service for the `DWRN2LV` keyword value:

```
hires{hireseng}61: show -s hiccd DWRN2LV
                       DWRN2LV = 10.618933 percent full
```

By calling `show` with the `-s` argument and then specifying the `hiccd` service and `DWRN2LV` keyword, I get the information I want.  Note, in this example, the `DWRN2LV` keyword can not be modified.

Another example would be the raw encoder count position of the HIRES cross disperser angle.  To view the current position I would query the `hires` service for the `XDRAW` keyword:

```
hires{hireseng}62: show -s hires XDRAW
                         XDRAW = -1373 encoder pulses
```

The `XDRAW` value is able to be modified.  I could do that with the `modify` command and then verify the final position with `show`:

```
hires{hireseng}63: modify -s hires XDRAW=-1000
setting XDRAW = -1000 (wait)
hires{hireseng}64: show -s hires XDRAW
                         XDRAW = -997 encoder pulses
```

Note that while I have followed the convention of writing the service name in lowercase and the keyword name in all caps, this is not necessary as the commands are case insensitive.

There are other commands for keywords:

* `xshow` will pop up a small window with one or more keywords and their values and will continuously update them.  This is basically a very simple status GUI.
* `cshow` will continuously show the keyword value, printing a new line whenever the value is updated and is a good way to monitor a changing situation.
* `gshow` is not always available, it tends to be installed on newer machines only.  It is a more modern and capable version of `show` and has many options.  For services which have a keyword history monitor, `gshow` can display a history of the keyword values and even generate simple plots of the values over time.
