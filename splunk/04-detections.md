# Detection Engineering

## Overview

Detection engineering is the process of developing searches and logic that identify potentially suspicious activity from security telemetry.

In this lab, Splunk SPL is used to search endpoint telemetry and identify security-relevant events.

The initial detection work focuses on Windows authentication activity.

## Detection Environment

| Component | Value |
|---|---|
| SIEM | Splunk Enterprise |
| Endpoint | Windows 10 |
| Telemetry | Windows Event Logs + Sysmon |
| Index | `endpoint` |
| Domain | `haruna.lab` |

## Detection 1 — Windows Failed Logon

### Objective

Identify failed Windows authentication attempts using Security Event ID 4625.

### SPL

```spl
index=endpoint EventCode=4625
