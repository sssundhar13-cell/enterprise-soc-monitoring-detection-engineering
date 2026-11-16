
# Active Directory and DNS Configuration

## 1. Overview

Active Directory Domain Services (AD DS) was configured to provide centralized identity and domain management within the SOC lab.

The Windows Server 2019 virtual machine acts as the Domain Controller.

## 2. Domain Configuration

| Component | Configuration |
|---|---|
| Server | Windows Server 2019 |
| Domain | soclab.local |
| Domain Controller | DC01 |
| Directory Service | Active Directory Domain Services |
| DNS | Active Directory-integrated DNS |

## 3. Organizational Unit Structure

The following organizational units and default containers are present:

- Users_Accounts (custom OU)
- Servers (custom OU)
- Users (built-in container)
- Computers (built-in container)

The custom OUs provide a basic structure for organizing domain accounts and servers.

## 4. DNS Configuration

The Domain Controller uses its local DNS service for domain name resolution.

The DNS client configuration was updated to use the loopback address after AD DS promotion.

## 5. DNS Resolution Verification

The following command was used to verify domain name resolution:

```powershell
ipconfig /flushdns
nslookup soclab.local
```

The domain name successfully resolved to the Domain Controller.

## 6. Windows Endpoint Domain Authentication

The Windows 11 endpoint was configured as part of the SOC lab domain environment.

A domain user account was used to sign in to the endpoint.

When the Domain Controller was unavailable, cached domain credentials allowed the user to sign in.

## 7. Security Monitoring Relevance

Active Directory provides identity and authentication context for endpoint security monitoring.

Relevant Windows security events can be collected and analyzed through Wazuh.
