# SOC Lab Security Testing and Validation

## 1. Testing Overview

Security testing was conducted within an isolated and authorized VMware SOC lab environment.

The objective was to validate firewall traffic filtering, centralized log collection, and Wazuh custom alert generation.

## 2. Nmap Network Testing

Kali Linux was used as the authorized testing machine.

The test focused on TCP ports 80 and 443 of the Windows 11 lab endpoint.

Example command:

```bash
nmap -Pn -sT -p 80,443 <LAB_ENDPOINT_IP>
```

## 3. Firewall Validation

OPNsense monitored the incoming connection attempts and applied its firewall filtering rules.

Observed results:

- TCP port 80: Filtered
- TCP port 443: Filtered
- Firewall action: Block

The firewall logs recorded the corresponding blocked connection attempts.

## 4. Wazuh Alert Validation

OPNsense firewall logs were forwarded to the Ubuntu SOC server.

Wazuh processed the events and generated alerts using the custom detection rule.

| Attribute | Observed Result |
|---|---|
| Custom Rule ID | 100050 |
| Severity | 10 |
| Event Source | OPNsense Firewall |
| Action | block |
| Target | Windows 11 lab endpoint |

## 5. Endpoint Monitoring Validation

Sysmon and the Wazuh agent were verified on the Windows 11 endpoint.

Observed security event categories included:

- Process creation
- Failed login events
- Endpoint security activity

## 6. Validation Outcome

The lab demonstrated the following security monitoring workflow:

1. Generate controlled network connection attempts.
2. Evaluate traffic using OPNsense firewall rules.
3. Record blocked connections in firewall logs.
4. Forward firewall logs to Wazuh.
5. Generate custom security alerts.
6. Review the resulting alerts in Wazuh Threat Hunting.

## 7. Security Scope

All testing was performed against systems owned and controlled within the authorized lab environment.

Sensitive internal network details and credentials are excluded from this public documentation.
