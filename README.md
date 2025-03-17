# sbdm-cli
Get life time expectation for WAGO memory card
The Swissbit Device Manager (SBDM) is a utility program that reads status information from memory card supporting S.M.A.R.T (Self-Monitoring, Analysis and Reporting Technology).
The tool can be used to extrapolate the life time expectation of a memory card in a real application by taking two snapshots before and after the test and evaluating the consumption through the test phase.

More information : https://www.swissbit.com/en/support/swissbit-device-manager/

```
curl -k -o sbdm-cli https://raw.githubusercontent.com/quenorha/sbdm-cli/refs/heads/main/sbdm-cli && chmod +x sbdm-cli
```


```
Usage: ./sbdm-cli [options] [mode] [device]
Options:
 -h, --help, -? Displays help on commandline options.
 -v, --version Displays version information.
 -q, --quiet No textual output except errors. For
 firmware update, this enforces unattended
mode (read-only).
 -o, --output, -l, --list <list> Information output mode, can be "human"
 (default) or "csv". Supported for LTM mode
only.
 -f, --fw <file> Firmware package to use for firmware update.
 If this option is omitted, the tool will
search firmware package automatically. Can be
provided multiple times for multiple
packages.
 --db <db> LTM mode only, sets database sbdm.db file
 usage, can be "auto", "no" or "yes".
Arguments:
 mode Mode to use. Available are "ltm" to get
 device data and "fwupdate" for firmware
update.
"fwupdate-force" is an unattended mode with
forced update execution, "fwupdate-query" is
an unattended mode to query for possible
updates only.
Unknown keywords will be treated as [device]
arguments in mode "ltm".
 device Device to use. Provide the full device path
 (i.e. /dev/sdx).
```
