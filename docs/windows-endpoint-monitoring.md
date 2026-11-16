
# Windows Endpoint Monitoring

## 1. Overview

Windows 11 Pro is configured as the monitored endpoint in the Enterprise SOC Lab.

The endpoint integrates with the central Wazuh Manager through the Wazuh Agent. Sysmon provides additional Windows system activity telemetry for security monitoring and investigation.

## 2. Endpoint Components

| Component | Purpose |
|---|---|
| Windows 11 Pro | Monitored endpoint |
| Wazuh Agent | Forwards endpoint security events |
| Sysmon | Collects detailed system activity |
| Windows Event Logs | Provides operating system security events |

## 3. Wazuh Agent Integration

The Wazuh Agent is installed on the Windows 11 endpoint and registered with the Ubuntu SOC Server.

The agent collects configured endpoint events and forwards them to the Wazuh Manager for analysis.

## 4. Sysmon Integration

Sysmon is used to collect detailed Windows system activity.

The monitoring scope includes:

- Process creation events
- Process execution details
- Image and executable information
- Relevant Windows event telemetry

## 5. Security Monitoring

The collected endpoint telemetry supports:

- Process activity monitoring
- Suspicious execution investigation
- Windows security event analysis
- Centralized alert generation through Wazuh

## 6. Event Analysis

Collected Windows events can be reviewed through the Wazuh Dashboard and used for security investigation.

Sysmon Event ID 1 represents process creation and is useful for analyzing executable activity.

## 7. Verification

Endpoint integration should be verified by checking:

- Wazuh Agent connection status
- Sysmon service status
- Windows Event Viewer
- Wazuh alerts generated from endpoint events
