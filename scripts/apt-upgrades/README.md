# apt-upgrades

Shows the number of packages awaiting upgrade on the local system. If the list contains any security upgrades, then the number is formatted with a different (red by default) background.

## Example Config

You can use it as follows;

```ini
[module/apt-upgrades]
type = custom/script
exec = ~/polybar-scripts/apt-upgrades
format-prefix = "APT: "
click-left = xterm -hold -e apt list --upgradable 
interval = 600
```

## Installation and Dependencies

Requires `apt` - the standard packaging tool on Debian and Ubuntu based systems.
