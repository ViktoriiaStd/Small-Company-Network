# Small-Company-Network
Small company network simulation with VLANs, DHCP, ACLs, and switch security.

This project simulates a small company network with multiple departments, demonstrating core networking concepts including VLANs, inter-VLAN routing, DHCP, ACLs, and switchport security. It is designed as a beginner network engineer project to showcase practical skills in configuring and securing a corporate network.

---

## Project Overview

**Company Requirements:**
- Three departments: HR, Sales, IT
- Each department has its own VLAN
- All PCs must have internet access
- Security rules with ACLs:
  - HR cannot access IT
  - Only IT can access the Server
- Router-on-a-Stick for inter-VLAN routing
- ISP router simulates internet access

**Skills Demonstrated:**
- VLAN creation and assignment
- Router-on-a-stick inter-VLAN routing
- DHCP pool configuration per VLAN
- Extended ACL implementation
- Switchport security with sticky MAC addresses
- IP addressing and network design
- Packet Tracer simulation and verification

---

```
Repository Structure
Small-Company-Network/
├── README.md
├── packet-tracer/
│ └── small_company_network.pkt
├── screenshots/
│ ├── topology.png
│ ├── vlan_brief.png
│ ├── trunk_config.png
│ ├── router_subinterfaces.png
│ ├── dhcp_binding.png
│ ├── acl_deny.png
│ ├── acl_allow.png
│ ├── port_security_interfaces.png
│ ├── port_security_mac.png
│ └── port_security_violation.png
```

---

## Screenshots

### `topology.png`
**Network topology overview**  
Logical topology of a small company network showing router-on-a-stick inter-VLAN routing, two switches connected via trunk, four VLANs (HR, Sales, IT, Server), and end devices assigned per department.

### `vlan_brief.png`
**VLAN configuration on access switch**  
Output of `show vlan brief` confirming correct VLAN creation and assignment of access ports to their respective departments.

### `trunk_config.png`
**Trunk configuration between switches**  
Output of `show interfaces trunk` verifying that trunk ports allow VLANs 10, 20, 30, and 40 for inter-switch and router communication.

### `router_subinterfaces.png`
**Router subinterfaces (inter-VLAN routing)**  
Output of `show ip interface brief` showing router subinterfaces configured with 802.1Q encapsulation and acting as default gateways for each VLAN.

### `dhcp_binding.png`
**DHCP address assignment**  
End devices successfully receive IP addresses via DHCP from the router, confirming correct DHCP pool configuration per VLAN.

### `acl_deny.png`
**ACL enforcement — HR to IT blocked**  
Ping test from HR VLAN to IT VLAN fails as expected, demonstrating extended ACL blocking unauthorized inter-department communication.

### `acl_allow.png`
**ACL verification — IT to Server / Sales to HR allowed**  
Ping tests succeed from allowed VLANs, confirming that ACL rules are applied directionally and other traffic is permitted.

### `port_security_interface.png`
**Switchport security configuration**  
Output of `show port-security interface` confirming that port security is enabled with sticky MAC learning, maximum one MAC address, and violation mode set to restrict.

### `port_security_mac.png`
**Sticky MAC address learning**  
Output of `show port-security address` displaying dynamically learned sticky MAC addresses bound to specific switch ports.

### `port_security_violation.png` 
**Port security violation detection**  
Security violation triggered by connecting an unauthorized device, demonstrating protection against rogue hosts.

---

## How to Run / Verify

1. Open `small_company_network.pkt` in Cisco Packet Tracer.
2. Verify VLANs and trunking on switches.
3. Check router subinterfaces for inter-VLAN routing.
4. Ping between devices to verify ACL restrictions.
5. Confirm DHCP address assignment to all end devices.
6. Test switchport security by connecting a device to a secured port.

---

## Project Outcome

- All VLANs correctly configured and assigned.
- Router-on-a-stick provides inter-VLAN routing.
- DHCP pools automatically assign IPs to devices.
- ACLs enforce department-specific security rules.
- Switchport security prevents unauthorized device connections.
- Packet Tracer simulation confirms expected behavior for all scenarios.

