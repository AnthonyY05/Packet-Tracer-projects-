# Network Troubleshooting Lab | Cisco Packet Tracer

## Project Overview

This project demonstrates practical network troubleshooting using Cisco Packet Tracer.

I created a two-network environment connected through a Cisco router and deliberately introduced several configuration faults.

I then used networking commands and a structured troubleshooting process to identify, resolve and verify each issue.

---

## Network Topology

![Network Troubleshooting Lab](Topology%20NTL.png)

### Network Design

#### LAN 1

- PC1: `192.168.10.10`
- Default Gateway: `192.168.10.1`
- Subnet Mask: `255.255.255.0`

#### LAN 2

- PC2: `192.168.20.10`
- Default Gateway: `192.168.20.1`
- Subnet Mask: `255.255.255.0`

#### Router

- GigabitEthernet0/0: `192.168.10.1`
- GigabitEthernet0/1: `192.168.20.1`

---

## Baseline Connectivity Test

Before introducing any faults, I confirmed that communication between PC1 and PC2 was working correctly.

I tested connectivity using:

```text
ping 192.168.20.10
```

The successful ping confirmed that the network was functioning correctly before troubleshooting began.

![Baseline Working Network](00-baseline-working..png)

---

## Troubleshooting Tools Used

- `ping`
- `ipconfig`
- `show ip interface brief`
- `show interfaces status`
- Cisco IOS CLI
- Cisco Packet Tracer

---

# Fault 1: Incorrect IP Address

PC2 was unable to communicate with its default gateway.

## Investigation

I tested connectivity using:

```text
ping 192.168.20.1
```

The ping failed.

![Incorrect IP Failed Ping](01-wrong-ip-failed-ping.png)

I then checked the IP configuration using:

```text
ipconfig
```

I identified that PC2 had been incorrectly configured as:

```text
192.68.20.10
```

Instead of:

```text
192.168.20.10
```

![Incorrect IP Identified](02-wrong-ip-identified.png)

## Resolution

I corrected PC2 to:

- IP Address: `192.168.20.10`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.20.1`

I then tested connectivity again:

```text
ping 192.168.20.1
```

Connectivity was successfully restored.

![Incorrect IP Fixed](03-wrong-ip-fixed.png)

---

# Fault 2: Incorrect Default Gateway

PC1 was deliberately configured with an incorrect default gateway.

Incorrect gateway:

```text
192.168.10.254
```

Correct gateway:

```text
192.168.10.1
```

## Investigation

I tested communication between PC1 and PC2:

```text
ping 192.168.20.10
```

The ping failed.

![Wrong Gateway Failed Ping](04-wrong-gateway-failed-ping.png)

I then checked the PC configuration using:

```text
ipconfig
```

This showed that the default gateway was incorrect.

![Wrong Gateway Identified](05-wrong-gateway-identified.png)

## Resolution

I changed the default gateway back to:

```text
192.168.10.1
```

I then tested communication again:

```text
ping 192.168.20.10
```

Connectivity between the two networks was restored.

![Wrong Gateway Fixed](06-wrong-gateway-fixed.png)

---

# Fault 3: Router Interface Shutdown

The router interface connecting LAN 2 was deliberately shut down.

## Investigation

I checked the router interfaces using:

```text
show ip interface brief
```

The GigabitEthernet0/1 interface showed as administratively down.

![Router Interface Down](07-router-interface-down.png)

I then tested communication from PC1 to PC2:

```text
ping 192.168.20.10
```

The ping failed.

![Interface Down Failed Ping](08-interface-down-failed-ping.png)

## Resolution

I restored the router interface using:

```text
enable
configure terminal
interface gigabitEthernet0/1
no shutdown
end
```

I then verified the interface status again:

```text
show ip interface brief
```

The interface returned to an `up/up` state.

![Router Interface Restored](09-router-interface-restored.png)

I then tested end-to-end connectivity again:

```text
ping 192.168.20.10
```

The ping was successful.

![Interface Fixed Ping](10-interface-fixed-ping.png)

---

# Fault 4: Incorrect Subnet Mask

PC1 was deliberately configured with an incorrect subnet mask.

Incorrect subnet mask:

```text
255.255.0.0
```

Correct subnet mask:

```text
255.255.255.0
```

With the incorrect subnet mask, PC1 incorrectly treated the `192.168.20.0` network as being part of its local network.

## Investigation

I tested connectivity from PC1 to PC2:

```text
ping 192.168.20.10
```

The ping failed.

![Incorrect Subnet Mask Failed Ping](12-subnet-mask-failed-ping.png)

I then checked the IP configuration using:

```text
ipconfig
```

This showed that PC1 was configured with the incorrect subnet mask:

```text
255.255.0.0
```

![Incorrect Subnet Mask Identified](11-wrong-subnet-mask.png)

## Resolution

I restored the subnet mask to:

```text
255.255.255.0
```

I then tested connectivity again:

```text
ping 192.168.20.10
```

Connectivity was successfully restored.

![Subnet Mask Fixed](13-subnet-mask-fixed.png)

---

# Final Network Verification

After resolving all introduced faults, I restored the network to its intended configuration.

### PC1

```text
IP Address:      192.168.10.10
Subnet Mask:     255.255.255.0
Default Gateway: 192.168.10.1
```

### Router

```text
G0/0: 192.168.10.1
G0/1: 192.168.20.1
```

Both router interfaces were confirmed as:

```text
up/up
```

### PC2

```text
IP Address:      192.168.20.10
Subnet Mask:     255.255.255.0
Default Gateway: 192.168.20.1
```

A final end-to-end connectivity test confirmed that the network was functioning correctly.

![Final Network Working](14-final-network-working.png)

---

# Troubleshooting Methodology

Rather than changing configurations randomly, I used a structured troubleshooting process:

```text
Identify
↓
Test
↓
Isolate
↓
Correct
↓
Verify
```

For each fault, I tested connectivity at different points in the network to determine where communication stopped.

This allowed me to isolate the cause of each issue before making configuration changes.

---

# Skills Demonstrated

- IPv4 addressing
- Subnetting
- Default gateway configuration
- Cisco router configuration
- Cisco switch troubleshooting
- Cisco IOS commands
- Router interface troubleshooting
- Network connectivity testing
- Fault isolation
- Ping testing
- IP configuration analysis
- Structured troubleshooting
- End-to-end connectivity verification
- Cisco Packet Tracer

---

# Faults Troubleshot

| Fault | Cause | Troubleshooting Method | Resolution |
|---|---|---|---|
| Incorrect IP address | PC2 configured as `192.68.20.10` | `ipconfig` and `ping` | Corrected to `192.168.20.10` |
| Incorrect default gateway | PC1 gateway set to `192.168.10.254` | `ipconfig` and `ping` | Corrected to `192.168.10.1` |
| Router interface shutdown | G0/1 administratively disabled | `show ip interface brief` | Used `no shutdown` |
| Incorrect subnet mask | PC1 configured with `255.255.0.0` | `ipconfig` and connectivity testing | Restored `255.255.255.0` |

---

# Project Outcome

This lab helped develop my ability to troubleshoot network connectivity systematically rather than making configuration changes without first identifying the cause.

The project demonstrates how common networking problems including incorrect IP addressing, incorrect default gateways, disabled router interfaces and incorrect subnet masks can be diagnosed and resolved using Cisco networking tools.

It also reinforced the importance of verifying connectivity after each configuration change to confirm that the problem has been fully resolved.

---

# Project File

The complete Cisco Packet Tracer project is included in this repository.

```text
NetworkTroubleshootingLab.pkt
```

Cisco Packet Tracer is required to open the `.pkt` file.
