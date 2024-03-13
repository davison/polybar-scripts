# pacman-upgrades

Shows the number of core and extra packages awaiting upgrade on the local system. 


## Example Config

You can use it as follows;

```ini
[module/pacman-upgrades]
type = custom/script
exec = ~/polybar-scripts/pacman-upgrades
format-prefix = "PKG: "
click-left = xterm -hold -e checkupdates
interval = 3600
```

In the example shown, clicking on the bar will open a read-only xterm showing which packages are the ones requiring the upgrade.


## Installation and Dependencies

Requires `extra/pacman-contrib` - additional scripts for working with `pacman` on Arch.
