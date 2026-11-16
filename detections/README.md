# Custom Detection Engineering

This directory documents custom security detection logic developed and validated in the SOC lab.

## Custom Rule: 100050

| Attribute | Value |
|---|---|
| Rule ID | 100050 |
| Severity Level | 10 |
| Base Rule | 87700 |
| Detection Source | OPNsense Firewall Logs |
| Event Action | block |
| Detection Purpose | Identify blocked traffic targeting the protected Windows endpoint |

## Detection Logic

The custom rule evaluates decoded firewall events and matches blocked traffic directed towards the protected endpoint.

## Validation

The detection was tested using authorized Nmap TCP connection attempts against ports 80 and 443.

The observed firewall block events were received and processed by Wazuh.

## Evidence

Related screenshots are maintained in the `screenshots` directory.

## Security Note

Internal IP addresses and environment-specific configuration values are excluded from this public documentation.
