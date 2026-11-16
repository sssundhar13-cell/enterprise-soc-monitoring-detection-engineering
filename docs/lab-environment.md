
# SOC Lab Environment

## 1. Host Environment

The SOC lab is deployed using VMware Workstation on a Windows host system.

| Resource | Configuration |
|---|---|
| Hypervisor | VMware Workstation |
| Host RAM | 16 GB |
| Host CPU | 4 cores |
| Deployment Type | Virtualized Lab Environment |

## 2. Virtual Machines

| Virtual Machine | Operating System | Primary Function |
|---|---|---|
| Ubuntu SOC Server | Ubuntu Server 24.04 | Centralized Wazuh monitoring |
| Windows 11 Endpoint | Windows 11 Pro | Endpoint telemetry collection |
| Domain Controller | Windows Server 2019 | Active Directory and DNS |
| Firewall | OPNsense | Network traffic filtering |
| Testing Machine | Kali Linux | Authorized security testing |

## 3. Security Components

### Ubuntu SOC Server
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

### Windows 11 Endpoint
- Wazuh Agent
- Sysmon
- Windows Security Event Logging

### Windows Server 2019
- Active Directory Domain Services
- DNS Server
- Domain authentication

### OPNsense
- Firewall rules
- Network traffic filtering
- Firewall event logging
- Syslog integration

### Kali Linux
- Nmap
- Authorized network scanning
- Firewall rule validation

## 4. Lab Deployment Model

All components operate as virtual machines within a VMware-based lab environment.

The environment is designed to demonstrate centralized security monitoring, endpoint event collection, firewall log analysis, and detection validation.

## 5. Configuration Verification

Virtual machine resource allocations, network adapter assignments, and IP configurations should be verified against the actual VMware configuration before deployment or modification.
