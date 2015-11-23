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

## Troubleshooting

If some tab bars aren't hidden, you may need to modify your drawing engine style (but all
the default styles appear to work).  Drawing engine styles are usually defined in files
named `look_foo.lua`.  You can try adding
```lua
de.defstyle("frame-tiled-alt", {
    bar = "none",
})

de.defstyle("frame-unknown-alt", {
    bar = "none",
})

de.defstyle("frame-floating-alt", {
    bar = "none",
})

de.defstyle("frame-transient-alt", {
    bar = "none",
})
```

## License

[LGPLv3](http://www.gnu.org/licenses/lgpl-3.0.en.html)

<!--- vim: set tw=90 sts=-1 sw=4 et spell: -->
