
# Custom Sigma Detection Rules

This directory contains custom Sigma detection rules developed for the Enterprise SOC Monitoring and Detection Engineering Lab.

## Implemented Sigma Rules

| Rule File | Detection Purpose | MITRE ATT&CK |
|---|---|---|
| custom_certutil_download.yml | Suspicious Certutil download activity | T1105 |
| custom_suspicious_powershell.yml | Encoded PowerShell command execution | T1059.001 |

## Rule Details

### 1. Suspicious Certutil Download Activity

Detects certutil.exe process execution with URL or download-related command-line arguments.

### 2. Suspicious PowerShell Encoded Command Execution

Detects PowerShell process creation involving encoded command arguments.

## Additional Artifact

The custom_suspicious_powershell_lucene.txt file contains a Lucene query associated with the PowerShell detection.

## Validation Status

The Sigma YAML files were created in the lab. Conversion, SIEM deployment and end-to-end validation are not confirmed in this documentation.

## Security Notice

These rules are intended for authorized SOC lab detection engineering and educational use.
