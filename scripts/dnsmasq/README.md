# dnsmasq

[dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) is a common DNS accelerator installed locally to cache heavily reused DNS queries. It can be queried for a number of interesting stats on hit or miss rates and cache insertions and evictions. This polybar script enables the polybar config to show one or more of these stats by passing a "command" argument to the script which determines the stat to return and display.

## Example Config

You can use it as follows;

```ini
[module/dnsmasq]
type = custom/script
exec = ~/polybar-scripts/dnsmasq hits
label = "DNS: "
```

The argument supplied to the script (`hits` in the example above) is a command that can be varied to obtain different information about the local dns cache. If no command is supplied, it defaults to `hits`.

Available commands are;

* `hits` (default) - the raw number of successful cache hits since the last cache restart
* `misses` - the raw number of unsuccessful cache requests that had to be sent upstream for an answer
* `insertions` - the total number of unique hostnames that have been inserted into the cache since the last cache restart
* `evictions` - the total number of unique hostnames that have had to be evicted from the cache PRIOR to a TTL timeout (a number higher than 0 probably indicates a cache size that is too small)
* `ratio` - the % of successful `hits` out of the total number of cache requests: `hits / (hits + misses) x 100`

## Installation and Dependencies

Requires `dig` and `bc` to work (`sudo apt install bc bind9-dnsutils` or equivalent for your OS and package manager).
