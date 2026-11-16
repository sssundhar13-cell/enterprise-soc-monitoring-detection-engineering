
# Enterprise SOC Monitoring and Detection Engineering Lab

## 1. Project Overview

The Enterprise SOC Monitoring and Detection Engineering Lab is a virtualized cybersecurity environment designed to demonstrate Security Operations Center (SOC) monitoring, endpoint security monitoring, firewall log analysis, and custom threat detection.

The project integrates multiple virtual machines to simulate essential components of an enterprise security monitoring environment.

## 2. Project Objectives

- Implement centralized security monitoring using Wazuh.
- Collect Windows endpoint telemetry using Sysmon and the Wazuh Agent.
- Monitor firewall activity through OPNsense logs.
- Configure Active Directory and DNS using Windows Server 2019.
- Develop and validate custom Wazuh detection rules.
- Perform authorized network security testing using Kali Linux.
- Visualize security alerts through the Wazuh Dashboard.

## 3. Lab Components

| Component | Operating System | Purpose |
|---|---|---|
| SOC Server | Ubuntu Server 24.04 | Wazuh Manager, Indexer and Dashboard |
| Endpoint | Windows 11 Pro | Endpoint monitoring and Sysmon telemetry |
| Domain Controller | Windows Server 2019 | Active Directory and DNS |
| Firewall | OPNsense | Network traffic filtering and logging |
| Testing Machine | Kali Linux | Authorized security testing |

## 4. Core Technologies

- Wazuh
- Sysmon
- OPNsense
- Active Directory
- DNS
- VMware
- Kali Linux
- Nmap
- XML-based Wazuh custom detection rules

## 5. Detection and Monitoring Scope

The lab focuses on the following security monitoring activities:

- Windows endpoint event monitoring.
- Process creation event collection.
- Firewall allowed and blocked traffic monitoring.
- Custom firewall detection rule implementation.
- Network scanning activity validation.
- Security alert visualization and analysis.

## 6. Project Outcome

The project demonstrates how endpoint telemetry and firewall logs can be centrally collected, analyzed, and visualized using a Wazuh-based SOC monitoring environment.

It also demonstrates practical detection engineering through custom rule development and authorized security testing.

## 7. Project Scope

This project is developed for educational and practical cybersecurity skill development in an isolated virtual lab environment. All security testing is performed against authorized lab systems.
