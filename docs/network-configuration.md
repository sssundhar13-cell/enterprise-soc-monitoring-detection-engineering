
# SOC Lab Network Configuration

## 1. Network Overview

The SOC lab uses VMware virtual networking to connect the security monitoring server, Windows endpoints, domain controller, firewall, and authorized testing machine.

The network infrastructure supports endpoint communication, centralized log collection, firewall monitoring, and security testing.

## 2. Network Components

| Component | Network Role |
|---|---|
| Ubuntu SOC Server | Centralized security log collection |
| Windows 11 | Monitored endpoint |
| Windows Server 2019 | Active Directory and DNS |
| OPNsense | Network traffic filtering |
| Kali Linux | Authorized security testing |

## 3. VMware Virtual Networks

The lab uses VMware virtual network interfaces, including NAT and Host-only networking.

| Virtual Network | Network Type | Purpose |
|---|---|---|
| VMnet5 | Host-only | Isolated host and VM communication |
| VMnet8 | NAT | Network access through host NAT |

Verify the current VMware Virtual Network Editor configuration before relying on these network assignments.

## 4. Network Communication

### Endpoint Monitoring
Windows 11 communicates with the Ubuntu SOC Server through the Wazuh Agent to forward endpoint security events.

### Firewall Monitoring
OPNsense forwards firewall log events to the Ubuntu SOC Server using Syslog integration.

### Domain Services
Windows 11 communicates with Windows Server 2019 for Active Directory authentication and DNS services when the Domain Controller is available.

### Security Testing
Kali Linux performs authorized network scanning against the lab environment to validate firewall traffic filtering and security alert generation.

## 5. Network Security

- Network traffic is controlled through firewall rules.
- Security testing is restricted to authorized lab systems.
- Firewall events are centrally monitored through Wazuh.
- Endpoint security events are collected through the Wazuh Agent.

## 6. IP Addressing

Actual IP addresses, subnet masks, gateways, and interface assignments must be documented from the verified current lab configuration.

Do not use historical IP addresses without confirming that they are still assigned.

## 7. Verification

Network connectivity and communication paths should be validated using appropriate tools such as:

- `ipconfig`
- `ip addr`
- `ping`
- `nslookup`
- `nmap`

Successful connectivity and firewall behavior should be confirmed through actual test results.
