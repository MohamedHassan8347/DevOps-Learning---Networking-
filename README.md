# DevOps-Learning---Networking-
Repo entailing my experience and findings from learning about networking


## Overview
Over the course of my learning, I’ve explored the fundamentals of computer networking, key 
components, protocols, IP addressing, and network troubleshooting, with a focus on relevance 
to a DevOps role. This summary consolidates my understanding, practical tools, and day-to-day 
commands.

---

## 1. Networking Basics
- A **network** is a connection of devices (computers, servers, IoT devices) that communicate 
with each other.  
- Devices communicate via **IP addresses** (identifying devices on a network) and **MAC 
addresses** (unique hardware identifiers).  
- Devices can have multiple MAC addresses for different network interfaces (e.g., Wi-Fi, 
Ethernet).  
- **Ports** and **protocols** define how data is transmitted:
  - TCP → reliable, connection-oriented communication  
  - UDP → faster, connectionless communication  

---

## 2. Networking Components
- **Routers**: Direct traffic between networks.  
- **Switches**: Connect multiple devices in the same local network.  
- **Firewalls**: Control incoming/outgoing traffic and enforce security policies.  
- **Servers**: Provide services like web hosting, DNS, or databases.  
- **Load balancers**: Distribute traffic to multiple servers to ensure availability.  

---

## 3. DNS (Domain Name System)
- **DNS** translates human-readable domain names into IP addresses.  
- Key components:
  - **Records**: A, AAAA, CNAME, MX, TXT, etc.  
  - **Zone files**: Define DNS records for a domain.  
- Commands for troubleshooting DNS:
```bash
3 nslookup example.com
dig example.com

/etc/hosts can override DNS resolution for testing purposes.```


## 4. Routing & NAT

Routing: How data packets find the best path from source to destination.

Static routing: Routes manually configured.

Dynamic routing: Routes automatically updated by protocols like OSPF or BGP.

NAT (Network Address Translation): Allows multiple devices with private IPs to access the 
internet via a single public IP.

---


``` 4 Commands for routing and connectivity:
ip route        # Check routing table
ping <host>     # Test connectivity
traceroute <host>  # Trace packet path ```


## 5. IP Addressing & Subnetting

Private IPs: Used inside homes or company networks to conserve public IPs and improve 
security.

Subnetting divides a large network into smaller, manageable segments.

CIDR notation indicates network vs host bits.
Example: 192.168.1.0/24 → 24 bits network, 8 
bits host

---


``` 5 - Commands to inspect IP configuration:

ifconfig        # View local interfaces (macOS/Linux)
ip addr show    # Alternative command for IP info```

---


## 6. Network Troubleshooting

Common issues: connectivity problems, DNS failures, IP conflicts, routing errors, firewall 
blocks.

---

```6 DevOps tools for troubleshooting:

ping <host>          # Test connectivity
traceroute <host>    # Trace path to host
nslookup <domain>    # Check DNS resolution
dig <domain>         # Advanced DNS queries
tcpdump -i eth0      # Capture packets for analysis
netstat -rn          # View routing tables and active connections ```

---

## 7. Practical DevOps Relevance

Networking knowledge is crucial for:

Cloud deployments (AWS VPCs, private/public subnets)

Firewall/security group configuration

DNS management and load balancing

Debugging CI/CD pipelines and microservices communication

---


## 8. Summary

By learning networking concepts from IP addressing, subnets, NAT, routing, DNS, and 
troubleshooting tools, I now understand how to:

Map internal vs external services in a network

Diagnose connectivity and DNS issues

Use command-line tools for DevOps workflows

Apply these skills to real-world cloud and enterprise environments

---
