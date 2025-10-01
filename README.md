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
nslookup example.com
dig example.com 
```

---

## 4. Routing & NAT

Routing: How data packets find the best path from source to destination.

Static routing: Routes manually configured.

Dynamic routing: Routes automatically updated by protocols like OSPF or BGP.

NAT (Network Address Translation): Allows multiple devices with private IPs to access the 
internet via a single public IP.

```
 Commands for routing and connectivity
ip route             # Check routing table
ping <host>          # Test connectivity
traceroute <host>    # Trace packet path
```

## 5. IP Addressing & Subnetting

Private IPs: Used inside homes or company networks to conserve public IPs and improve 
security.

Subnetting: Divides a large network into smaller, manageable segments.

CIDR notation: Indicates network vs host bits.
Example: 192.168.1.0/24 → 24 bits network, 8 bits host

---

```
Commands to inspect IP configuration
ifconfig           # View local interfaces (macOS/Linux)
ip addr show       # Alternative command for IP info
```

## 6. Network Troubleshooting

Common issues: connectivity problems, DNS failures, IP conflicts, routing errors, firewall 
blocks.

---

```
 DevOps tools for troubleshooting 
ping <host>          # Test connectivity
traceroute <host>    # Trace path to host
nslookup <domain>    # Check DNS resolution
dig <domain>         # Advanced DNS queries
tcpdump -i eth0      # Capture packets for analysis
netstat -rn          # View routing tables and active connections
```
##7. Practical DevOps Relevance

Networking knowledge is crucial for:

Cloud deployments (AWS VPCs, private/public subnets)

Firewall/security group configuration

DNS management and load balancing

Debugging CI/CD pipelines and microservices communication

---

##8. Summary

By learning networking concepts from IP addressing, subnets, NAT, routing, DNS, and 
troubleshooting tools, I now understand how to:

Map internal vs external services in a network

Diagnose connectivity and DNS issues

Use command-line tools for DevOps workflows

Apply these skills to real-world cloud and enterprise environments
---

# Deploying NGINX on AWS EC2

This section documents the process of creating an **EC2 instance** running 
**NGINX** on **port 80**, along with the significance of this exercise for 
DevOps learning.

---

## Steps to Create an EC2 Instance with NGINX

1. **Launch EC2 Instance**
   - Log in to the AWS Management Console.
   - Navigate to **EC2 → Launch Instance**.
   - Select an AMI (Amazon Linux 2 or Ubuntu recommended).
   - Choose an instance type (e.g., t2.micro for testing).

2. **Select VPC and Subnet**
   - Choose a **VPC** (default is fine for testing).
   - Select a **public subnet** to allow internet access.
   - Enable **auto-assign public IP**.

3. **Configure Security Group**
   - Add an inbound rule for **HTTP (port 80)**.
   - Optionally, allow **SSH (port 22)** for access.

4. **Connect via SSH**
   ```bash
   chmod 400 nginx.pem
   ssh -i "nginx.pem" ec2-user@ec2-44-223-102-42.compute-1.amazonaws.com

```
sudo amazon-linux-extras enable nginx1
sudo yum install -y nginx

To start and enable NGINX 
sudo systemctl start nginx
sudo systemctl enable nginx


To verify that it has been done, I opened a browser and inputted my EC2 
public IP. I was met with a webpage stating: Welcome to NGINX! The nginx 
web server has been successfully installed.

## Importance for DevOps

Infrastructure Provisioning: Demonstrates how to spin up cloud resources 
in AWS.

Networking Understanding: Shows the role of VPCs, subnets, and security 
groups in exposing services.

Web Server Deployment: NGINX is widely used to serve static content, 
reverse proxy requests, and load balance applications.

Validation & Monitoring: Ensures your instance is correctly configured and 
reachable.

Foundation for Automation: Lays the groundwork for scripting deployments 
with Terraform, Ansible, or CI/CD pipelines.  
