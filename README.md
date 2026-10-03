# Splunk SOC Home Lab

A hands-on Security Operations Center (SOC) home lab built to develop practical skills in security monitoring, log collection, detection engineering, incident investigation, Windows security, Active Directory, Linux, and Splunk.

## Project Overview

This project simulates a small enterprise security monitoring environment using virtual machines.

The lab is designed to demonstrate how security telemetry can be collected from endpoints, forwarded to a SIEM, analyzed, and used to investigate suspicious activity.

## Objectives

- Deploy and configure Splunk Enterprise
- Configure Windows endpoint monitoring
- Deploy Sysmon for detailed Windows telemetry
- Configure Splunk Universal Forwarder
- Collect Windows Security and Sysmon events
- Build security detections using SPL
- Investigate authentication failures
- Practice incident investigation workflows
- Understand Active Directory security monitoring
- Develop practical SOC analyst skills
- Document troubleshooting and lessons learned

## Lab Architecture

```text
                    Internet
                       |
                 VMware VMnet8
                    NAT
                       |
              Windows Server 2025
                    DC01
             AD DS + DNS + DHCP
                    |
               VMnet1 / LAN
             192.168.56.0/24
                    |
       +------------+------------+
       |            |            |
   Windows 10     Kali       Splunk Server
   Endpoint       Linux       Splunk Enterprise
   + Sysmon                    + SIEM
   + UF
