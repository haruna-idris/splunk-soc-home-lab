# Security Data Ingestion

## Overview

This document describes how security telemetry is collected from the Windows 10 endpoint and ingested into Splunk Enterprise.

The ingestion pipeline uses Sysmon, Windows Event Logs, Splunk Universal Forwarder, and Splunk Enterprise.

## Architecture

```text
Windows 10
    |
    +--> Sysmon
    |
    +--> Windows Security Event Log
    |
    v
Splunk Universal Forwarder
    |
    | TCP 9997
    v
Splunk Enterprise
    |
    v
index=endpoint
