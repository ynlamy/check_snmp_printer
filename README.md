# check_snmp_printer

This plugin can check your printer consumables status using SNMP v1 queries.

check_snmp_printer is written in Bash and is distributed under the GPLv2 license. This plugin have been created by Yoann LAMY.

## Usage
```
check_snmp_printer [options] | -h | -V
```

## Options

| Option     | Description                                                       |
| ---------- | ----------------------------------------------------------------- |
| -H ADDRESS | Name or IP address of host (default: 127.0.0.1)                   |
| -C STRING  | Community name for the host's SNMP agent (default: public)        |
| -t STRING  | Check type (consumable, page) (default: page)                     |
| -o STRING  | Consummable (black, cyan, magenta, yellow, drum) (default: black) |
| -w INTEGER | Warning level for the checked resource (default: 0)               |
| -c INTEGER | Critical level for the checked resource (default: 0)              |
| -v         | Enable verbose mode, printing raw output from SNMP                |
| -d         | Enable debugging output                                           |
| -h         | Print this help screen                                            |
| -V         | Print version and license information                             |

The warning and critical levels are intepreted differently, depending on the type of resource.
For pages, the values are absolute (i.e. raise alerts at a particular number of printed pages).
For consumables, the value is interpreted as percent used.

## Examples

```
./check_snmp_printer -H xxx.xxx.xxx.xxx -C public -t consummable -o black -w 85 -c 90
./check_snmp_printer -H xxx.xxx.xxx.xxx -C public -t page
```

This nagios plugins comes with ABSOLUTELY NO WARRANTY.

You may redistribute copies of the plugins under the terms of the GNU General Public License v2. 
