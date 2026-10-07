# Cyberlab-Kali-Linux-and-Nmap

## Overview
This project will document a small lab built to practice cybersecurity fundamentals relevant to system security roles. Using Kali Linux and a target (another VM) I will perform network discovery and enumeration to better understand attack reduction and verification.

## Key Objectives
- Learn basic Linux tools
- Practice host and service discovery with Nmap
- Investigate what processes were bound to open ports
- Verify remediation through rescanning procedures
- Reduce attack surfaces

## Environment

- Kali Linux VM
- Ubuntu [Target VM]
- Isolated local virtual network

## Tools Used
- Nmap
- Linux
- ss
- ps
- curl
- A Python 3 HTTP server [for testing]

## Procedures

## 1. Identifying Network Configuration

The first step was identifying the network configuration of both systems.

I used:

```bash
ip addr
ip route
```

This allowed me to identify each system's IPv4 address, network interface,
and routing configuration.

### Kali Linux

Kali was used as the system performing network reconnaissance and testing.

![Kali network configuration](screenshots/kaliinfocyberlab.png)

### Ubuntu Target

Ubuntu served as the target system for the lab.

![Ubuntu network configuration](screenshots/ubuntuinfocyberlab.png)

### What I Learned

`ip addr` displays information about the network interfaces configured on a
Linux system, while `ip route` displays how the system determines where
network traffic should be sent.

---

## 2. Testing Connectivity

Before performing network scans, I ensured that Kali can communicate with Ubuntu.

```bash
ping -c 4 <TARGET-IP>
```

![Connectivity test](screenshots/pingservercyberlab.png)

The target successfully responded to the requests, confirming that
the two systems could communicate.

This established basic connectivity before moving on to service discovery.

---

## 3. Initial Port Discovery

After confirming connectivity, I used Nmap to examine the target system.

```bash
nmap <TARGET-IP>
```

![Initial Nmap scan](screenshots/nmapubuntucyberlab.png)

### Findings

The scan demonstrated that Nmap could determine which TCP ports were reachable
from the Kali system.

This is important because exposed ports can indicate network-accessible
services that should be investigated.

---
# Findings [WIP]
