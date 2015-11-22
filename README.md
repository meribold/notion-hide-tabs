# hide_tabs.lua

Lua script for the [Notion window manager][1] that hides the tab bar of frames which
contain exactly one client window.  Tagged frames are excluded.

If you've used [min_tabs.lua][2], this script's advantages are:
* It doesn't define a hard-coded (or any) keybinding
* It works for the sratchpad
* It recovers from exiting Notion without closing all client windows first more gracefully

[1]: https://github.com/raboof/notion
[2]: https://github.com/raboof/notion/blob/master/contrib/scripts/min_tabs.lua

## Installation

Copy `hide_tabs.lua` to `~/.notion/`
```sh
curl -fLo ~/.notion/hide_tabs.lua \
    https://raw.githubusercontent.com/meribold/notion-hide-tabs/master/hide_tabs.lua
```
and enable it by adding `dopath("hide_tabs")` to
(usually) your `cfg_notion.lua`.

You need a drawing engine style that defines some `-alt` styles with `bar = "none"` for
frames.  If you've used `min_tabs.lua` you should already have those.  If not, drawing
engine styles are usually defined in files named `look_foo.lua`.  To modify your existing
style, you might add
```lua
de.defstyle("frame-tiled-alt", {
    based_on = "frame-tiled",
    bar = "none",
})

de.defstyle("frame-unknown-alt", {
    based_on = "frame-unknown",
    bar = "none",
})

de.defstyle("frame-floating-alt", {
    based_on = "frame-floating",
    bar = "none",
})

de.defstyle("frame-transient-alt", {
    based_on = "frame-transient",
    bar = "none",
})
```

## License

LGPLv3

<!--- vim: set tw=90 sts=-1 sw=4 et spell: -->
