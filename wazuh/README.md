# Wazuh Custom Detection Rules

This directory contains sanitized Wazuh detection rule examples developed for the SOC lab.

## Rule 100050 – Firewall Block Detection

| Attribute | Value |
|---|---|
| Rule ID | 100050 |
| Severity | 10 |
| Parent Rule | 87700 |
| Event Source | OPNsense Firewall |
| Action | block |
| Detection Objective | Identify blocked traffic targeting the protected endpoint |

## Detection Logic

The rule uses decoded firewall event fields to identify blocked traffic directed towards the protected endpoint.

## Testing and Validation

The detection was validated in the private SOC lab using controlled Nmap TCP connection attempts against ports 80 and 443.

The corresponding firewall events were received and processed by Wazuh.

## Configuration Note

The published XML uses a documentation IP placeholder.

Replace it with the appropriate protected endpoint address when adapting the rule to another lab.

## Security

Do not publish real internal IP addresses, credentials, API keys, or sensitive network configuration.
