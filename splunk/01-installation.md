# Splunk Enterprise Installation

## Overview

Splunk Enterprise is the central SIEM platform in this SOC home lab.

It receives security telemetry from the Windows 10 endpoint through the Splunk Universal Forwarder, stores the events in the `endpoint` index, and provides the platform used for searching, detection engineering, and investigation.

## Splunk Server

Splunk Enterprise is deployed on a dedicated Ubuntu virtual machine.

| Configuration | Value |
|---|---|
| Hostname | Splunk01 |
| Operating System | Ubuntu Server 24.04 LTS |
| Architecture | x86-64 |
| IP Address | 192.168.56.20 |
| Network | VMnet1 |
| Role | Splunk Enterprise SIEM |

## Installation

Splunk Enterprise was installed on the Splunk01 virtual machine.

The installation package used was:

```text
splunk-10.4.3-4174a2deda5d-linux-amd64.deb
