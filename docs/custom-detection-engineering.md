
# Custom Detection Engineering

## 1. Overview

Custom detection engineering was implemented to identify firewall-blocked network traffic targeting the protected Windows 11 endpoint.

The detection logic uses Wazuh custom rules to analyze OPNsense firewall events and generate security alerts.

## 2. Detection Rule Details

| Attribute | Value |
|---|---|
| Rule ID | 100050 |
| Severity Level | 10 |
| Base Rule | 87700 |
| Detection Source | OPNsense Firewall Logs |
| Event Action | block |
| Target Endpoint | Windows 11 |
| Detection Platform | Wazuh |

## 3. Detection Logic

The custom rule uses the following conditions:

- The event must match the base firewall rule 87700.
- The firewall action must be `block`.
- The destination IP must match the protected Windows 11 endpoint: `192.168.10.10`.

When all conditions match, Wazuh generates an alert with Rule ID 100050 and severity level 10.

## 4. Custom Rule Configuration

The rule was configured in:

`/var/ossec/etc/rules/local_rules.xml`

The configuration was validated using the Wazuh analysis engine test command before restarting the manager.

## 5. Rule Validation

The following validation command was executed:

```bash
sudo /var/ossec/bin/wazuh-analysisd -t
```

The Wazuh manager was restarted after configuration validation and verified to be running.

## 6. Detection Testing

An authorized Nmap TCP connect scan was performed from the Kali Linux testing machine against the Windows 11 endpoint.

Test command:

```bash
nmap -Pn -sT -p 80,443 192.168.10.10
```

OPNsense firewall logs recorded blocked traffic targeting the Windows 11 endpoint.

The corresponding firewall events were processed by Wazuh, and the custom detection rule generated alerts.

## 7. Detection Verification

The generated alert was verified in Wazuh using Rule ID 100050.

The alert contained relevant information such as:

- Source IP
- Destination IP
- Firewall action
- Rule ID
- Alert severity

The dashboard was also configured to visualize these custom firewall detection alerts.

## 8. Security Significance

This implementation demonstrates how firewall telemetry can be integrated into centralized security monitoring.

It also demonstrates the use of custom detection logic to identify and prioritize suspicious blocked network activity.

**Note:** A firewall-block alert indicates that traffic was blocked. It does not independently prove that the source performed a successful intrusion.
