# SOC Lab Architecture

## 1. Architecture Overview

The Enterprise SOC Monitoring and Detection Engineering Lab is designed to demonstrate centralized security monitoring, endpoint telemetry collection, firewall log analysis, and custom threat detection.

The environment uses multiple virtual machines connected through a virtualized network infrastructure.

## 2. Lab Components

| Component | Operating System | Primary Role |
|---|---|---|
| SOC Server | Ubuntu Server 24.04 | Wazuh Manager, Indexer and Dashboard |
| Endpoint | Windows 11 Pro | Endpoint monitoring and Sysmon telemetry |
| Domain Controller | Windows Server 2019 | Active Directory and DNS |
| Firewall | OPNsense | Network traffic filtering and firewall logging |
| Testing Machine | Kali Linux | Authorized security testing |

## 3. Logical Architecture Diagram

```text
             KALI LINUX
          (Security Testing)
                  |
                  | Nmap Test Traffic
                  v
          OPNSENSE FIREWALL
                  |
          +-------+--------+
          |                |
     Allowed Traffic    Firewall Logs
          |                |
          v                v
    WINDOWS 11        UBUNTU SOC SERVER
    (Agent + Sysmon)  (Wazuh Manager)
          |                |
          |                v
          |          WAZUH INDEXER
          |                |
          |                v
          |         WAZUH DASHBOARD
          |
          | Active Directory / DNS
          |
          v
    WINDOWS SERVER 2019
       (DC01)
```
