# Security Testing and Validation

## 1. Testing Overview

Security testing was conducted within an isolated and authorized VMware SOC lab environment.

The objective was to validate firewall traffic filtering, centralized log collection, endpoint monitoring, and Wazuh custom alert generation.

## 2. Nmap Network Testing

Kali Linux was used as the authorized testing machine to generate network scan traffic targeting the Windows 11 endpoint.

Test command:

```bash
nmap -Pn -sT -p 80,443 <LAB_ENDPOINT_IP>
```

The test targeted TCP ports 80 and 443.

## 3. Firewall Validation

OPNsense firewall logs were examined to verify how the generated network traffic was handled.

The test demonstrated blocked TCP traffic targeting the Windows 11 endpoint.

## 4. Wazuh Alert Validation

Firewall events were forwarded to the Ubuntu SOC Server for centralized monitoring.

Wazuh processed the firewall events and generated alerts using the custom detection rule.

| Attribute | Observed Value |
|---|---|
| Custom Rule ID | 100050 |
| Severity Level | 10 |
| Firewall Action | block |
| Source IP | <KALI_LAB_IP> |
| Destination IP | <LAB_ENDPOINT_IP> |

## 5. Endpoint Monitoring Validation

Windows 11 endpoint telemetry was collected through the Wazuh agent and Sysmon.

Process creation events (Sysmon Event ID 1) were monitored and visualized in the Wazuh dashboard.

## 6. Detection Verification

The following results were verified:

- Nmap test traffic was generated from Kali Linux.
- OPNsense recorded blocked network traffic.
- Wazuh processed the firewall events.
- Custom Rule ID 100050 generated security alerts.
- Sysmon process creation events were collected from Windows 11.
- Security events were available in the Wazuh dashboard.

## 7. Conclusion

The testing validated the integration of network security monitoring, firewall log analysis, endpoint telemetry collection, and custom detection engineering.

The lab demonstrates a basic end-to-end SOC monitoring and detection workflow.

**Note:** These tests validate monitoring and blocking behavior in the lab. They do not demonstrate a successful compromise of the Windows endpoint.
