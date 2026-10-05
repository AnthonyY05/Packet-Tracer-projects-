# Packet-Tracer-projects-
My Cisco Packet Tracer networking labs and projects
# Cisco Packet Tracer Portfolio

A collection of practical networking projects created using Cisco Packet Tracer.

These projects demonstrate hands-on experience with network configuration, troubleshooting, IP addressing, switching, routing, VLANs and connectivity testing.

---

## Small Office Network

A basic small office network designed to practise core networking and IT support skills.

### Key Skills

- IPv4 addressing
- DHCP
- Subnetting
- Router configuration
- Switch configuration
- Default gateways
- Connectivity testing
- Basic troubleshooting

### Project Summary

The network includes:

- 1 Cisco router
- 1 Cisco 2960 switch
- 5 PCs
- DHCP for automatic IP addressing

The router was configured with the `192.168.1.0/24` network and tested using tools such as `ipconfig` and `ping`.

[View Small Office Network Project](Small-Office-Network/)

---

## Network Troubleshooting Lab

A practical troubleshooting lab built to diagnose and resolve common network connectivity issues.

### Faults Investigated

- Incorrect IP address
- Incorrect default gateway
- Disabled router interface
- Incorrect subnet mask

### Troubleshooting Tools

- `ping`
- `ipconfig`
- `show ip interface brief`
- `show interfaces status`
- Cisco IOS CLI

### Project Summary

The network was intentionally misconfigured several times to simulate realistic faults.

Each issue was worked through using a structured troubleshooting process:

`Identify → Test → Isolate → Correct → Verify`

Screenshots were used to document the failed connectivity, diagnosis and successful resolution of each problem.

[View Network Troubleshooting Lab](Network-Troubleshooting-Lab/)

---

## Office VLAN Project

A segmented office network using separate VLANs for Admin, Sales and IT departments.

### Key Skills

- VLAN configuration
- Access ports
- 802.1Q trunking
- Router-on-a-stick
- Inter-VLAN routing
- Router subinterfaces
- Network segmentation
- IPv4 addressing
- Connectivity testing

[View Office VLAN Project](Office-VLAN-Project/)

---

## Skills Demonstrated Across Projects

- Cisco Packet Tracer
- IPv4 addressing
- Subnetting
- DHCP
- VLANs
- Trunking
- Router-on-a-stick
- Inter-VLAN routing
- Router configuration
- Switch configuration
- Cisco IOS
- Network troubleshooting
- Connectivity testing
- Fault isolation

---

## DNS and Web Server Lab

A simple client server networking project demonstrating DNS name resolution and basic web services in Cisco Packet Tracer.

### Key Skills

- DNS configuration
- DNS A records
- HTTP services
- IPv4 addressing
- Client server networking
- Connectivity testing
- Name resolution
- Basic troubleshooting

### Project Summary

A DNS and web server was configured at `192.168.1.10`.

Client PCs were configured to use the server for DNS and successfully accessed the hosted website using both:

`192.168.1.10`

and:

`www.company.local`

The project also included command line testing to verify that the hostname correctly resolved to the server IP address.

[View DNS and Web Server Lab](DNS-Web-Server-Lab/)

## DHCP Troubleshooting Lab

A practical Cisco Packet Tracer lab focused on configuring and troubleshooting DHCP within a small client server network.

### Key Skills

- DHCP configuration
- DHCP pools
- IPv4 addressing
- Subnetting
- Automatic IP assignment
- Client server networking
- Connectivity testing
- Fault isolation
- Network troubleshooting

### Project Summary

A DHCP server was configured to automatically provide IP addresses and network settings to client PCs on the `192.168.50.0/24` network.

The lab included troubleshooting several common DHCP problems, including:

- DHCP service disabled
- Clients receiving addresses from the wrong network
- Incorrect subnet mask configuration
- DHCP pool exhaustion

Tools such as `ipconfig` and `ping` were used to identify faults, verify client configuration and confirm connectivity after each resolution.

[View DHCP Troubleshooting Lab](DHCP-Troubleshooting-Lab/)


## Multi Department Company Network

A larger Cisco Packet Tracer project combining VLANs, routing and network services within a simulated business environment.

### Key Skills

- VLAN configuration
- Network segmentation
- 802.1Q trunking
- Router-on-a-stick
- Inter-VLAN routing
- DHCP and DHCP relay
- DNS
- HTTP services
- Access Control Lists
- IPv4 addressing
- Cisco IOS
- Network troubleshooting

### Project Summary

A company network was designed for Admin, Sales, HR, IT and Server departments using separate VLANs and subnets.

A central server provided DHCP, DNS and internal web services, while router subinterfaces enabled inter-VLAN communication.

DHCP relay was configured so clients in different VLANs could obtain addresses from the central DHCP server.

An ACL was also introduced to prevent Sales users from directly accessing the HR network while maintaining access to shared company services.

[View Multi Department Company Network](Multi-Department-Company-Network/)
## Portfolio Goal

This portfolio documents my practical development in networking and IT infrastructure.

Each project focuses on building, configuring, testing and troubleshooting network environments while developing hands-on experience with Cisco technologies and core networking concepts.
