# Custom Sigma Detection Rule Drafts

This directory contains draft Sigma detection rules and a related Lucene query prepared for the Enterprise SOC Monitoring and Detection Engineering Lab.

## Rule Files

| Rule File | Detection Purpose | MITRE ATT&CK |
|---|---|---|
| custom_certutil_download.yml | Suspicious Certutil download activity | T1105 |
| custom_suspicious_powershell.yml | Encoded-command or download-related PowerShell execution | T1059.001, T1027 |

## Rule Details

### 1. Suspicious Certutil Download Activity

Detects `certutil.exe` process execution when the command line contains URL-cache and HTTP indicators.

### 2. Suspicious PowerShell Execution

Detects PowerShell or PowerShell 7 process creation involving encoded-command arguments or download-related command strings.

## Additional Artifact: Lucene Query

The `custom_suspicious_powershell_lucene.txt` file contains a Lucene query intended to search for encoded PowerShell command activity.

The query assumes that indexed events expose the fields `process.executable.caseless` and `process.command_line`. Confirm the actual index mappings and available fields before using it.

## Validation Status

These files are draft repository artifacts. The following work remains pending:

- Validate both YAML files with a Sigma-compatible parser.
- Confirm that the selected log source and field names match the actual Windows event data.
- Convert or independently implement the detection logic for the target SIEM.
- Deploy only after rule review and test in the lab.
- Perform controlled test events and verify the expected alerts.
- Tune false positives based on observed results.

Uploading a Sigma file to GitHub does not by itself mean that the rule is deployed or producing alerts in Wazuh.

## Security Notice

These rules are intended for authorized SOC lab detection engineering and educational use.
