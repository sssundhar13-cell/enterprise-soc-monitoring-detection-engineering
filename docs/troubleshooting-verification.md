
# Troubleshooting and Verification

## 1. Overview

This document records selected troubleshooting activities and verification procedures performed during the Enterprise SOC Monitoring and Detection Engineering Lab implementation.

## 2. Wazuh Manager Service Verification

The Wazuh Manager service was checked after configuration changes.

Verification command:

```bash
sudo systemctl status wazuh-manager
```

The service was verified to be active and running after the custom detection rule configuration.

## 3. Wazuh Configuration Validation

The Wazuh analysis engine configuration was tested before restarting the manager.

Validation command:

```bash
sudo /var/ossec/bin/wazuh-analysisd -t
```

The validation command completed without reporting configuration errors.

## 4. Firewall Log Collection Verification

Wazuh archive logging was enabled by setting `logall_json` to `yes` in:

`/var/ossec/etc/ossec.conf`

The Wazuh Manager was restarted, and the archive log file was checked:

`/var/ossec/logs/archives/archives.json`

The presence of archived firewall events was verified.

## 5. Custom Detection Rule Verification

Custom Rule ID `100050` was tested using the Wazuh log testing utility.

The rule was designed to match blocked firewall traffic targeting the protected Windows 11 endpoint.

The test confirmed that matching BLOCK events triggered the custom rule, while PASS events did not.

## 6. Wazuh Agent Verification

The Windows 11 endpoint was monitored through the Wazuh agent.

The agent connection status was checked through the Wazuh environment, and the endpoint was identified as `LUPIN_AGENT`.

## 7. Dashboard Verification

The Wazuh dashboard was checked to verify the availability of collected security events and custom firewall alerts.

The dashboard included visualizations for firewall alerts, alert types, login activity, MITRE ATT&CK techniques, and alert evolution.

## 8. Verification Summary

The following implementation areas were verified during the lab activities:

- Wazuh Manager service status
- Wazuh analysis engine configuration
- Firewall log archiving
- Custom detection rule behavior
- Windows endpoint agent monitoring
- SOC dashboard visualizations

## 9. Conclusion

These troubleshooting and verification activities helped validate the core SOC monitoring pipeline, from log collection and detection processing to security alert visualization.
