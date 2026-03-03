# Network Architecture Explanation

## Design Philosophy

The infrastructure was designed following enterprise security principles:

- Defense in Depth
- Least Privilege
- Segmentation
- High Availability
- Centralized Monitoring

---

## Why High Availability?

The Active/Passive Palo Alto cluster eliminates single points of failure.

If the primary firewall fails, the passive device automatically becomes active, ensuring continuous network operation.

---

## Why VLAN Segmentation?

VLANs isolate:

- User networks
- Server infrastructure
- Management systems
- Branch connections

This prevents lateral movement and limits attack surface.

---

## Why IPSec Site-to-Site VPN?

Branches communicate securely through encrypted tunnels over untrusted networks.

This protects data from interception and tampering.

---

## Why Centralized Monitoring?

Wazuh SIEM collects logs from:

- Domain Controller
- Firewall
- Linux systems
- VPN connections

This enables:

- Suspicious activity detection
- Centralized visibility
- Faster incident response

---

## Threat Mitigation Strategy

The architecture reduces risk of:

- Internal lateral movement
- Privilege escalation
- Unpatched vulnerabilities
- VPN interception attacks
- Service downtime

---

## Security Value of the Design

This topology simulates a real-world enterprise environment with layered protection, redundancy, and monitoring.

It demonstrates practical security engineering, not just service deployment.
