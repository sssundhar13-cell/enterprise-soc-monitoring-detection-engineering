# SOC Lab Configuration

This directory contains documentation about the configuration artifacts used in the Enterprise SOC Monitoring and Detection Engineering Lab.

## Configuration Status

- Wazuh custom firewall block detection rule is documented in the `wazuh/` directory.
- Wazuh Agent is configured on the Windows 11 endpoint.
- Sysmon is configured for Windows endpoint telemetry.
- OPNsense was configured for firewall traffic filtering and logging and was used during the documented firewall tests.

## Runtime Note

The OPNsense VM is currently powered off. The configuration documentation describes the previously configured lab setup and should not be interpreted as confirmation that the firewall is currently running.

## Security Notice

All published configuration information must be sanitized.

Credentials, API keys, private keys, authentication tokens, and sensitive information must not be published.
