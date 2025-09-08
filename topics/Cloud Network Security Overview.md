# Cloud Network Security Overview 

## What Is Cloud Network Security 
Cloud network security involves protecting cloud-based infrastructure from unauthorized access, data breaches, and cyberattacks by managing traffic flow, access controls, and segmentation. 

## Core Concepts to Learn
### Virtual Networking

- **VPC (Virtual Private Cloud):** Isolated cloud network environment.
- **Subnets:** Logical segmentation within a VPC.
- **Route Tables:** Define traffic flow between subnets and external networks.
- **NAT Gateways:** Enable outbound internet access for private subnets.

### Access Controls

- **Security Groups:** Stateful firewalls applied at the instance level.
- **Network ACLs (NACLs):** Stateless rules applied at the subnet level.
- **Cloud Firewalls & Microsegmentation:** Fine-grained traffic control between workloads.

### Connectivity & Trust

- **VPNs & Private Links:** Secure hybrid connectivity.
- **Zero Trust Architecture:** Assume breach; verify every access request. 

## Goals of Cloud Network Security

- **Segment resources** to reduce blast radius.
- **Control ingress/egress** to minimize exposure.
- **Prevent unauthorized access** through layered defenses.

## Tools & Hands-On Practice

### Platforms

- **AWS VPC**
- **Azure Virtual Networks (VNet)**
- **Palo Alto Firewalls**
- **Prisma Cloud**

### Practical Exercise

> Harden a public-facing web application:
> 
- Place app servers in **private subnets**.
- Use a **bastion host** for secure admin access.
- Apply **least privilege** security group rules.
- Monitor with **VPC Flow Logs** and **Prisma policies**.


## Best Practices

- Deny all by default; allow only necessary ports.
- Use private subnets for sensitive workloads.
- Apply least privilege to security group rules.
- Implement zero trust segmentation.
- Continuously monitor traffic and logs.

## Examples

- ✅ **Good SG Rule:** Allow port 443 only from trusted CIDR.
- ❌ **Bad SG Rule:** Open port 22 to `0.0.0.0/0`.

## Compliance Mapping

- **NIST 800-53:** SC-7 (Boundary Protection), SC-32 (Information Flow Enforcement)
- **CIS Controls:** 4.1 (Change Management), 4.3 (Secure Configuration)
- **SOC 2:** CC6.6 (Logical Access Controls)
