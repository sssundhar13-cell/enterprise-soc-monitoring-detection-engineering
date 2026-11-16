# Enterprise SOC Monitoring & Detection Engineering Lab

A hands-on Enterprise Security Operations Center (SOC) lab built using Wazuh, Sysmon, OPNsense, Active Directory, and Windows security telemetry.

This project demonstrates centralized security monitoring, endpoint log collection, firewall event analysis, custom detection engineering, and controlled attack simulation.

## Project Objectives

- Build a centralized SOC monitoring environment.
- Collect and analyze Windows endpoint security events.
- Monitor firewall traffic and blocked connections.
- Develop and validate custom Wazuh detection rules.
- Simulate controlled network scanning activity.
- Visualize security events through a SOC dashboard.

## Lab Architecture

The lab consists of the following components:

| Component | Purpose |
|---|---|
| Ubuntu Server | Wazuh Manager, Indexer and Dashboard |
| Windows 11 | Monitored endpoint |
| Windows Server 2019 | Active Directory and DNS |
| OPNsense | Network firewall and traffic monitoring |
| Kali Linux | Controlled security testing |

## Technologies Used

- Wazuh 4.14.8
- Sysmon
- OPNsense
- Windows 11
- Windows Server 2019
- Active Directory
- DNS
- Kali Linux
- VMware Workstation
- Custom Wazuh Rules
- Nmap

## Key Implementations

### 1. Centralized Security Monitoring

Configured Wazuh as the central monitoring platform to collect, process, and analyze security events from monitored systems.

### 2. Windows Endpoint Monitoring

Integrated a Windows 11 endpoint with Wazuh and Sysmon to collect process creation and endpoint activity telemetry.

### 3. Active Directory Environment

Configured a Windows Server 2019 Domain Controller with Active Directory Domain Services and DNS for centralized identity management in the lab.

### 4. Firewall Log Monitoring

Integrated OPNsense firewall logs with Wazuh to monitor allowed and blocked network traffic.

### 5. Custom Detection Engineering

Created and validated custom Wazuh rule ID `100050` to detect blocked traffic targeting the protected Windows endpoint.

The rule checks:
- Firewall action: `block`
- Destination: Protected lab endpoint
- Severity level: 10

### 6. Controlled Nmap Testing

Performed an authorized Nmap scan against the lab endpoint.

Tested ports:
- TCP 80
- TCP 443

The firewall blocked the tested connection attempts, and the corresponding events were detected by Wazuh.

### 7. SOC Dashboard

Created a custom Wazuh dashboard containing:
- Top agents
- Total security alerts
- Firewall block alerts
- Login status
- MITRE ATT&CK techniques
- Alert evolution
- Top alert types

## Detection Evidence

| Security Activity | Wazuh Rule ID |
|---|---:|
| Custom firewall block detection | 100050 |
| Sysmon process creation | 61603 |
| Failed login detection | 60122 |

## Project Status

Core SOC monitoring, endpoint telemetry, firewall log collection, custom detection, and controlled Nmap testing have been demonstrated.

Additional detection capabilities such as Sigma, YARA, and Suricata remain future development items until separately implemented and validated.

## Security Notice

This repository is intended for educational and authorized lab use.

Sensitive information such as credentials, API keys, internal network details, and personal data must not be published.

All testing was performed within an authorized lab environment.

## Author

Shanmuga Sundhar S

Cybersecurity | SOC Operations | Network Security | Digital Forensics
