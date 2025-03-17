# sbdm-cli
Get life time expectation for WAGO memory card
The Swissbit Device Manager (SBDM) is a utility program that reads status information from memory card supporting S.M.A.R.T (Self-Monitoring, Analysis and Reporting Technology).
The tool can be used to extrapolate the life time expectation of a memory card in a real application by taking two snapshots before and after the test and evaluating the consumption through the test phase.

More information : https://www.swissbit.com/en/support/swissbit-device-manager/

## How to install 
```
curl -k -o sbdm-cli https://raw.githubusercontent.com/quenorha/sbdm-cli/refs/heads/main/sbdm-cli && chmod +x sbdm-cli
```

## How to use
```
 ./sbdm-cli
Swissbit Device Manager 1.2.4

Please wait while SBDM is scanning for devices...


/dev/mmcblk0
------------

  Device information
    Model:                        SD card WA 0008G
    Serial:                       1622350047
    Firmware:                     160307 1.20
    Capacity:                     8GB
    Overall status:               PASS
    Health status:                PASS
    Data integrity status:        PASS

  Spare block information
    Spare block status:           PASS
    Remaining spare blocks:       100%
    Current spare blocks (total): 366
    Initial spare blocks (total): 366

  Erase count information
    Erase status:                 PASS
    Remaining erase life time:    100%
    Flash cell mode:              Native
    Average erase count:          12
    Total erase count:            49380

  Error correction information
    ECC Refresh Counter:          0
    Total flash read commands:    396913184
    Uncorrectable ECC errors:     0

  Power on counters
    Power on cycles:              677
    Power on data repairs:        0

  Advanced counters
    Initial bad block count:      24
    Flash block count:            4096
    Total LBA written:            142545223
    Total LBA read:               110610406
    Flash LBA written:            202260480
    Resulting WAF (Total):        1.4

  Interface
    Interface status:             PASS
    Current speed:                High Speed, 4 bit width
    Max. supported speed:         SD 3.0 UHS-I / High Speed / Default Speed
    Interface errors:             0

```



## Advanced usage
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
