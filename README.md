# sysmon-config

This is a template for the configuration of Microsoft (Sysinternals) Sysmon.

As stated in the original documentation of Sysmon
> System Monitor (Sysmon) is a Windows system service and device driver that, once installed on a system, remains resident across system reboots to monitor and log system activity to the Windows event log. It provides detailed information about process creations, network connections, and changes to file creation time. By collecting the events it generates using Windows Event Collection or SIEM agents and subsequently analyzing them, you can identify malicious or anomalous activity and understand how intruders and malware operate on your network.

Sysmon does not come with a user interface or any remote management capabilities, it needs to be run with a configuration file.

This project is meant to be a template with reasonable defaults. We hope that it serves the purpose as a starting point for a configuration that meets the requirements of your organisation. 

## Prerequisites
Aside from having the binary of Sysmon available on the local machine, you also need local administrator rights to run, (un-)install, or (re-)configure Sysmon.

## Customise
Please DO NOT USE THIS TEMPLATE without propper customisation! This template contains a lot of comments and is designed to be self-explanatory to assist in the process, but you need to make adjustments! If you run e.g. additional Endpoint Protection or Log-/SIEM-Agents on your machine, make sure to exclude them in the configuration - they will otherwise fill up your Event logs with useless or redundant information.

Please also check the latest documentation from Microsoft for additional parameters and/or options. 

## Use
Please run all commands with local administrator rights.

### Install
```
Sysmon64.exe -accepteula -i config.xml
```

```
System Monitor v12.01 - System activity monitor
Copyright (C) 2014-2020 Mark Russinovich and Thomas Garnier
Sysinternals - www.sysinternals.com

Loading configuration file with schema version 4.40
Configuration file validated.
Sysmon64 installed.
SysmonDrv installed.
Starting SysmonDrv.
SysmonDrv started.
Starting Sysmon64..
Sysmon64 started.
```

### Update
```
Sysmon64.exe -c config.xml
```

```
System Monitor v12.01 - System activity monitor
Copyright (C) 2014-2020 Mark Russinovich and Thomas Garnier
Sysinternals - www.sysinternals.com

Loading configuration file with schema version 4.40
Configuration file validated.
Configuration updated.
```

### Uninstall
```
Sysmon64.exe -u
```

```
System Monitor v12.01 - System activity monitor
Copyright (C) 2014-2020 Mark Russinovich and Thomas Garnier
Sysinternals - www.sysinternals.com

Stopping Sysmon64.
Sysmon64 stopped.
Sysmon64 removed.
Stopping SysmonDrv.
SysmonDrv stopped.
SysmonDrv removed.
Removing service files.
```

## Support
Please contact our [support team](mailto:help@threatint.com) for questions, comments, etc.

## References
- [Sysmon documentation and download](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)
- [SwiftOnSecurity/sysmon-config](https://github.com/SwiftOnSecurity/sysmon-config)

##
(C) Copyright 2021 [THREATINT (CYRRUS) LTD](https://threatint.eu)

## License
Release under the MIT License. (see LICENSE)
