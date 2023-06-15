# sysmon-config

# EOL
This respository is EOL (End-of-Life), we are no longer maintaining it. Most of our customers have implemented EDR (Endpoint Detection and Response), which has made the use of sysmon largely redundant.
Kindly send a message to [feedback@threatint.com](mailto:feedback@threatint.com), we are happy to reinstate this repository and work on it again if it is of any use (again).

## Introduction 
This is a template for the configuration of Microsoft (Sysinternals) Sysmon.

As stated in the original documentation of Sysmon
> System Monitor (Sysmon) is a Windows system service and device driver that, once installed on a system, remains resident across system reboots to monitor and log system activity to the Windows event log. It provides detailed information about process creations, network connections, and changes to file creation time. By collecting the events it generates using Windows Event Collection or SIEM agents and subsequently analyzing them, you can identify malicious or anomalous activity and understand how intruders and malware operate on your network.

Sysmon does not come with a user interface or any remote management capabilities, it needs to be run with a configuration file.

This project is meant to be a template with reasonable defaults. We hope that it serves the purpose as a starting point for a configuration that meets the requirements of your organisation. 

## Prerequisites
Aside from having the binary of Sysmon available on the local machine, you also need local administrator rights to run, (un-)install, or (re-)configure Sysmon.

## Customise
Please DO NOT USE THIS TEMPLATE without proper customisation! This template contains a lot of comments and is designed to be self-explanatory to assist in the process, but you need to make adjustments! If you run e.g. additional Endpoint Protection or Log-/SIEM-Agents on your machine, make sure to exclude them in the configuration - they will otherwise fill up your Event logs with useless or redundant information.

Please also check the latest documentation from Microsoft for additional parameters and/or options. 

## Running
Please run all commands with local admin rights. 

### Install
```
Sysmon.exe -accepteula -i config.xml
```

```
System Monitor v14.13 - System activity monitor
By Mark Russinovich and Thomas Garnier
Copyright (C) 2014-2022 Microsoft Corporation
Using libxml2. libxml2 is Copyright (C) 1998-2012 Daniel Veillard. All Rights Reserved.
Sysinternals - www.sysinternals.com

Loading configuration file with schema version 4.82
Sysmon schema version: 4.83
Configuration file validated.
Sysmon installed.
SysmonDrv installed.
Starting SysmonDrv.
SysmonDrv started.
Starting Sysmon..
Sysmon started.
```

### Update
```
Sysmon.exe -c config.xml
```

```
System Monitor v14.13 - System activity monitor
By Mark Russinovich and Thomas Garnier
Copyright (C) 2014-2022 Microsoft Corporation
Using libxml2. libxml2 is Copyright (C) 1998-2012 Daniel Veillard. All Rights Reserved.
Sysinternals - www.sysinternals.com

Loading configuration file with schema version 4.82
Sysmon schema version: 4.83
Configuration file validated.
Configuration updated.
```

### Uninstall
```
Sysmon.exe -u
```

```
System Monitor v14.13 - System activity monitor
By Mark Russinovich and Thomas Garnier
Copyright (C) 2014-2022 Microsoft Corporation
Using libxml2. libxml2 is Copyright (C) 1998-2012 Daniel Veillard. All Rights Reserved.
Sysinternals - www.sysinternals.com

Stopping Sysmon.
Sysmon stopped.
Sysmon removed.
Stopping SysmonDrv.
SysmonDrv stopped.
SysmonDrv removed.
Removing service files.
```

## References
- [Sysmon documentation and download](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)

## Feedback
We would love to hear from you! Please contact us at [help@threatint.com](mailto:help@threatint.com) for feedback and general requests.
Kindly raise an issue in Github if you find a problem in the code.

## License
Release under the MIT License. (see LICENSE)
