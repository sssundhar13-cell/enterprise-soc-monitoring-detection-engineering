# SOC Lab Architecture

## 1. Architecture Overview

The Enterprise SOC Monitoring and Detection Engineering Lab is designed to demonstrate centralized security monitoring, endpoint telemetry collection, firewall log analysis, and custom threat detection.

The diagram below documents the OPNsense-based logical topology used during the earlier firewall integration and detection tests.

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
                      | Nmap Scan Traffic
                      v
              OPNSENSE FIREWALL
                      |
             +--------+---------+
             |                  |
       Filtered Traffic     Firewall Logs
             |                  |
             v                  v
         WINDOWS 11        WAZUH MANAGER
      (Wazuh Agent +       (Ubuntu SOC Server)
          Sysmon)                 |
             |                   |
             +-------------------+
                                 |
                                 v
                          WAZUH INDEXER
                                 |
                                 v
                         WAZUH DASHBOARD


         WINDOWS 11
              |
              | AD Authentication / DNS
              |
              v
      WINDOWS SERVER 2019
       (Active Directory
            + DNS)
```

## 4. Runtime Status Note

The OPNsense VM is currently powered off. This diagram records the previously configured and tested logical topology; it does not indicate that the firewall is running now. Recheck interface assignments, routes, and firewall rules before bringing this topology back online.
