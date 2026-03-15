Virtual LAN (VLAN) Configuration and Management

Author

Name: Afreen Akram Shaikh 

---

Project Description

Virtual Local Area Network (VLAN) is a technology used to divide a physical network into multiple logical networks. VLANs help improve network performance, security, and traffic management.

In this project, three VLANs are configured on a switch, and each PC is assigned to a different VLAN. Inter-VLAN communication is enabled using the Router-on-a-Stick method.

---

Objectives

- Understand VLAN concepts
- Create multiple VLANs on a switch
- Assign switch ports to VLANs
- Configure trunk connection between switch and router
- Enable communication between different VLANs

---

Tools Used

- Cisco Packet Tracer
- Router
- Switch
- 3 PCs
- Ethernet cables

---

Network Topology

The network consists of:

- 1 Router
- 1 Switch
- 3 PCs connected to the switch
- 3 VLANs configured on the switch

Each PC belongs to a different VLAN.

---

VLAN Configuration

Step 1: Create VLANs

enable
configure terminal
vlan 10
name SALES
vlan 20
name HR
vlan 30
name IT
exit

---

Step 2: Assign Ports to VLANs

interface fa0/1
switchport mode access
switchport access vlan 10

interface fa0/2
switchport mode access
switchport access vlan 20

interface fa0/3
switchport mode access
switchport access vlan 30

---

Step 3: Configure Trunk Port

interface fa0/24
switchport mode trunk

---

Step 4: Configure Router-on-a-Stick

interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

interface g0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0

interface g0/0.30
encapsulation dot1Q 30
ip address 192.168.30.1 255.255.255.0

---

IP Addressing

Device| VLAN| IP Address
PC1| VLAN 10| 192.168.10.2
PC2| VLAN 20| 192.168.20.2
PC3| VLAN 30| 192.168.30.2

---

Verification Commands

show vlan brief
show ip interface brief
ping

---

Expected Output

- Three VLANs are successfully created.
- Each PC is assigned to a different VLAN.
- Communication between VLANs is enabled through the router.

---

Conclusion

This project demonstrates how VLANs can segment a network into smaller logical networks. By using Router-on-a-Stick, devices in different VLANs can communicate while maintaining network security and efficiency.

---

Repository Contents

- VLAN Packet Tracer file (.pkt)
- Configuration screenshots
- Project report
- README.md
