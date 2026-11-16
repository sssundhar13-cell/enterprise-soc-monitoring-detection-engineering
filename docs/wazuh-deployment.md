
# Wazuh Deployment and Configuration

## 1. Overview

Wazuh is the primary security monitoring platform deployed in the SOC lab.

It provides centralized security event collection, log analysis, security alert generation, and dashboard visualization.

## 2. Deployment Components

The Wazuh deployment consists of:

| Component | Responsibility |
|---|---|
| Wazuh Manager | Security event analysis and rule evaluation |
| Wazuh Indexer | Security event indexing and storage |
| Wazuh Dashboard | Security monitoring and visualization |
| Wazuh Agent | Endpoint event collection and forwarding |

## 3. SOC Server Environment

The Wazuh components are deployed on the Ubuntu SOC Server.

- Operating System: Ubuntu Server 24.04
- Wazuh Version: 4.14.8
- Hostname: UbuntuSocServer

## 4. Endpoint Integration

The Windows 11 endpoint is integrated with the Wazuh Manager through the Wazuh Agent.

The agent forwards collected endpoint security events to the central manager for analysis.

## 5. Firewall Log Integration

OPNsense firewall events are forwarded to the SOC Server through Syslog integration.

The Wazuh Manager analyzes the received firewall events using its configured decoders and rules.

## 6. Log Archiving

Wazuh event archiving was enabled through the `logall_json` configuration in the Wazuh Manager configuration file.

Archived events are written to:

`/var/ossec/logs/archives/archives.json`

## 7. Security Monitoring

The Wazuh Dashboard is used to visualize:

- Endpoint security alerts
- Firewall block events
- Windows process creation events
- Authentication-related events
- Custom detection alerts

## 8. Service Verification

Wazuh services should be verified using:

`systemctl status wazuh-manager`

`systemctl status wazuh-indexer`

`systemctl status wazuh-dashboard`

Service status must reflect the actual deployment state at the time of verification.
