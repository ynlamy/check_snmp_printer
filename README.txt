This plugin can check your printer consumables status using SNMP v1 queries.

check_snmp_printer is written in Bash and is distributed under the GPLv2 license. This plugin have been created by Yoann LAMY.

Usage: ./check_snmp_printer -H xxx.xxx.xxx.xxx -C public -t consummable -o black -w 85 -c 90

-H ADDRESS
Name or IP address of host (default: 127.0.0.1)
-C STRING
Community name for the host's SNMP agent (default: public)
-t STRING
Check type (consumable, page, model, serial) (default: page)
-o STRING
Consumable (black, cyan, magenta, yellow, drum) (default: black)
-w INTEGER
Warning level for consumable in percent (default: 0)
-c INTEGER
Critical level for consumable in percent (default: 0)
-X STRING
Overwrites OID used in check type PAGE, MODEL and SERIAL. Also used for check type CONSUMABLE (replaces OID_NAME)
-Y STRING
Overwrites OID used in check type CONSUMABLE (replaces OID_TOTAL)
-Z STRING
Overwrites OID used in check type CONSUMABLE (replaces OID_STATUS)
-n
Use SNMPGETNEXT instead of SNMPGET command
-h
Print this help screen
-V
Print version and license information

This plugin uses the 'snmpget' command and 'snmpwalk' command included with the NET-SNMP package.
This plugin support performance data output. If the percentage of the warning level and the critical level are 0, then the script returns a state OK.

Examples :

./check_snmp_printer -H xxx.xxx.xxx.xxx -C public -t consummable -o black -w 15 -c 10
./check_snmp_printer -H xxx.xxx.xxx.xxx -C public -t page

This nagios plugins comes with ABSOLUTELY NO WARRANTY.

You may redistribute copies of the plugins under the terms of the GNU General Public License v2. 
