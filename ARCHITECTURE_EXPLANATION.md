# Enterprise Security Architecture – Technical Deep Dive

## 1. Architecture Goals

The infrastructure was designed to simulate a real enterprise environment with:

- High Availability
- Secure inter-branch connectivity
- Centralized monitoring
- Active Directory hardening
- Privilege protection
- Patch & vulnerability management

The primary objective was to eliminate single points of failure while implementing layered security controls.

---

# 2. Perimeter Security Layer

## Palo Alto Active/Passive HA Cluster

The main office uses two Palo Alto firewalls configured in Active/Passive mode.

### HA Design Components

- HA1 – Control link (heartbeat, state monitoring)
- HA2 – Session synchronization
- Link monitoring
- Path monitoring

If:
- Active firewall fails
- Interface cable disconnects
- Critical path becomes unreachable

The passive device automatically becomes active.

This ensures business continuity.

---

# 3. Secure Branch Connectivity

## IPSec Site-to-Site VPN

Each branch is connected via IPSec VPN tunnels.

### Security Design

- IKE Phase 1 for authentication
- IPSec Phase 2 for encryption
- Crypto profiles defining:
  - Encryption algorithm
  - Authentication method
  - DH group
  - Lifetime

Traffic between branches is encrypted over untrusted networks.

This prevents:
- Man-in-the-middle attacks
- Traffic interception
- Data tampering

---

# 4. Network Segmentation Strategy

## VLAN-Based Segmentation

The network is divided into logical segments:

- User VLAN
- Server VLAN
- Management VLAN
- Branch VLAN

Benefits:

- Reduces lateral movement
- Limits blast radius
- Enforces zone-based firewall policies

Inter-VLAN traffic is controlled by the firewall.

---

# 5. Core Switching Layer

Core and branch switches are configured with:

- EtherChannel (Port-channel redundancy)
- Trunk links
- Access ports with security restrictions

Additional controls:

- Port Security
- DHCP Snooping
- STP configuration

This protects against:

- MAC flooding
- Rogue DHCP attacks
- Layer 2 manipulation

---

# 6. Identity & Access Management

## Active Directory Deployment

A centralized AD domain was deployed.

Security hardening includes:

- Organizational Unit structure per branch
- Group Policy enforcement
- Account lockout policies
- Password complexity enforcement

---

## Fine-Grained Password Policies (FGPP)

Different password policies were applied to specific groups.

Example:
- IT-Helpdesk: longer password lifetime
- Standard users: stricter expiration

This demonstrates granular identity control.

---

## LAPS Implementation

Local Administrator Password Solution was deployed.

Each domain-joined machine:

- Has a unique local admin password
- Password rotates automatically
- Stored securely in AD attributes

This mitigates:

- Pass-the-Hash attacks
- Lateral privilege escalation
- Shared local admin abuse

---

# 7. Centralized Monitoring & SIEM

## Wazuh SIEM

Log sources:

- Firewall
- Domain Controller
- Linux systems
- VPN events

Enables:

- Correlation of events
- Detection of brute-force attempts
- Suspicious authentication monitoring
- Policy violation tracking

---

# 8. Infrastructure Monitoring

## Zabbix

Used for:

- Availability monitoring
- Performance metrics
- Device health tracking

Prevents silent failures.

---

# 9. Patch & Endpoint Management

## ManageEngine Desktop Central

Used for:

- Patch deployment
- Software management
- Endpoint control
- Centralized device management

Reduces exposure to:

- Known CVEs
- Exploitable vulnerabilities
- Outdated software risks

---

# 10. Linux Integration

Linux systems were integrated into Active Directory.

Benefits:

- Centralized authentication
- Unified identity management
- Policy enforcement across OS platforms

---

# 11. Resilience & Defense-in-Depth Model

This architecture demonstrates:

Layer 1 – Perimeter security  
Layer 2 – Encrypted site-to-site communication  
Layer 3 – Network segmentation  
Layer 4 – Identity hardening  
Layer 5 – Endpoint patch management  
Layer 6 – Centralized monitoring  

No single control is trusted alone.

---

# 12. Real-World Security Value

This project reflects enterprise-grade design principles:

- High Availability
- Secure remote connectivity
- Identity-centric security
- Continuous monitoring
- Operational resilience

It simulates a production-ready corporate IT environment.
