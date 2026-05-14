## Objective
The objective of this lab was to configure Port Security on switch interfaces to prevent unauthorized devices from accessing the network
---

# Topology

![Topology](images/topology.png)

---

# Topics Covered
- Port Security
- Sticky MAC addresses
- MAC address learning
- Violation modes
- Unauthorized device detection
- Interface recovery
- Basic troubleshooting

---

# VLAN Configuration

| VLAN | Purpose |
|------|----------|
| 10 | Users |

---

# PC Addressing

| Device | IP Address |
|--------|------------|
| PC1 | 192.168.10.10 |
| PC2 | 192.168.10.20 |

---

# Port Security Configuration

## Interface Configuration

```bash
interface fa0/1
switchport mode access
switchport access vlan 10

switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
switchport port-security violation shutdown
```

---

# Verification Commands

```bash
show port-security
show port-security interface fa0/1
show running-config
```

---

# Port Security Verification

![Port Security Verification](images/secure-mac-learning.png)

---

# Security Violation Test

An unauthorized device was connected to the secured interface to simulate a real-world security violation.

The switch automatically placed the interface into a shutdown/error-disabled state to protect the network.

![Violation State](images/violation-state.png)

---

# Interface Recovery

The interface was restored using:

```bash
interface fa0/1
shutdown
no shutdown
```

# Troubleshooting

## Issue
The secured interface remained in an error-disabled state after reconnecting devices.

## Cause
Port Security detected a MAC address violation because a different device attempted to use the secured port.

## Fix
Recovered the interface using shutdown/no shutdown and verified the learned sticky MAC address configuration.

![Troubleshooting](images/troubleshooting.png)

---

# What I Learned
- How Port Security protects switch interfaces
- How sticky MAC address learning works
- How switches react to unauthorized devices
- How violation modes behave
- Basic switch security troubleshooting techniques

---

# Files Included
- Packet Tracer lab
- Configuration file
- Verification screenshots
- Troubleshooting screenshots
