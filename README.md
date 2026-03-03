# Secure Corporate IT Infrastructure with Centralized Monitoring

## Project Overview
This diploma project demonstrates the design and implementation of a secure enterprise IT infrastructure with centralized monitoring, high availability, and security controls.

## Network Architecture
- Palo Alto Firewall (Active/Passive HA)
- IPSec VPN tunnels between branches
- VLAN segmentation
- Core & Branch switches (EtherChannel, trunking)
- DHCP configuration

## Security Implementation
- IPSec VPN with IKE & Crypto profiles
- Wazuh SIEM integration (Syslog from firewall)
- Zabbix infrastructure monitoring
- Active Directory domain environment
- LAPS for local administrator password management
- Fine-Grained Password Policies
- Patch management via ManageEngine Desktop Central

## Additional Services
- Nextcloud (Private Cloud)
- Mattermost + LDAP integration
- 3CX IP Telephony
- Backup of network device configurations

## High Availability
- HA1 and HA2 synchronization
- Link & path monitoring
- Automatic failover between Active and Passive firewall

## Author
Inal Hajizada
STEP IT Academy

## Architecture Diagram

The network architecture includes:

- Core network with VLAN segmentation  
- Palo Alto Firewall in Active/Passive High Availability  
- IPSec VPN tunnels between headquarters and branch offices  
- Windows Server with Active Directory  
- Centralized logging (Wazuh SIEM)  
- Infrastructure monitoring (Zabbix)  
- Patch management system (ManageEngine)  

Topology diagram is available in this repository.
 A computer network diagram with blue lines and white text
![Network Topology](topology.png)
