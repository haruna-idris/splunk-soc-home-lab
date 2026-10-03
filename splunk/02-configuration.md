# Splunk Enterprise Configuration

## Overview

After installing Splunk Enterprise, the Splunk server was configured to receive and organize security telemetry from the Windows 10 endpoint.

The main configuration tasks included:

- Creating the `endpoint` index
- Configuring the receiving port
- Preparing Splunk to receive data from the Universal Forwarder
- Verifying network connectivity
- Verifying event ingestion

## Splunk Server

| Configuration | Value |
|---|---|
| Hostname | Splunk01 |
| Operating System | Ubuntu Server 24.04 LTS |
| IP Address | 192.168.56.20 |
| Splunk Web | Port 8000 |
| Forwarder Receiving Port | TCP 9997 |

## Network Connectivity

Splunk01 is connected to the internal VMware lab network:

```text
192.168.56.0/24
