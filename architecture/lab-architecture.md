# SOC Home Lab Architecture

## Overview

The SOC home lab is a virtualized enterprise-style environment built using VMware Workstation.

The lab contains a Windows Active Directory environment, Windows endpoint, Linux systems, Kali Linux, and a Splunk Enterprise SIEM.

The primary objective is to simulate the collection, forwarding, analysis, and investigation of security telemetry.

## Architecture

```text
                         INTERNET
                             |
                             |
                     VMware VMnet8
                       NAT Network
                     192.168.40.0/24
                             |
                             |
                    +----------------+
                    |      DC01      |
                    | Windows Server |
                    |     2025       |
                    +----------------+
                    | AD DS          |
                    | DNS            |
                    | DHCP           |
                    | RRAS / NAT     |
                    +----------------+
                             |
                             |
                     VMware VMnet1
                    192.168.56.0/24
                             |
            +----------------+----------------+
            |                |                |
            |                |                |
     +-------------+   +-------------+   +-------------+
     |  Windows 10 |   |    Kali     |   |  Splunk01   |
     |  Endpoint   |   |   Linux     |   |   Ubuntu    |
     +-------------+   +-------------+   +-------------+
     | Sysmon      |                       | Splunk     |
     | UF          |                       | Enterprise |
     +-------------+                       +-------------+
            |
            |
     Windows Event Logs
            |
            |
       TCP 9997
            |
            v
      Splunk Enterprise
            |
            v
      index=endpoint
            |
            v
   Detection & Investigation
