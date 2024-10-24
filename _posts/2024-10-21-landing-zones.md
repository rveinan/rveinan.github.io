---
title: "What is Azure Landing Zones?"
date: 2024-10-21 15:00:00 +0100
description: "Discover how Azure Landing Zones establish a secure, scalable foundation for deploying workloads in Azure."
categories: [Azure]
tags:
  [
    Microsoft Azure,
    Landing Zones
  ]
image:
  path: /assets/img/cloud.jpg
  src: /assets/img/cloud.jpg
---

## What is an Azure landing zone?

A landing zone is a well-architected environment that is highly scalable and secure. A landing zone allows you to accelerate moving workloads to the cloud whilst maintaining control and ensuring appropriate guardrails are in place. It is your cloud foundation, designed according to a set of best practices and guidelines, with a focus on key elements such as account and resource organisation, access management, network architecture, security and compliance, and logging/monitoring/auditing.

Azure Landing Zones adhere to these essential principles, including scalability, modularity, and security. These principles span eight key areas:

- **Azure Billing and Microsoft Entra Tenant**: Managing costs and subscriptions.
- **Identity and Access Management**: Ensuring secure access.
- **Resource Organisation**: Structuring subscriptions for efficiency.
- **Network Topology and Connectivity**: Designing robust networking.‍
- **Security**: Enforcing controls and compliance.‍
- **Management**: Streamlining operations.‍
- **Governance**: Defining policies.‍
- **Platform Automation and DevOps**: Accelerating deployment.

In your Azure tenant, a landing zone will be an area or a container where workloads (services) can operate. The landing zone is subject to a set of policies and restrictions that ensure everything operate within organizational guidelines and directives.

You can compare a landing zone to a room in a house. Each room in the house is unique to its purpose, just like products will be unique to each product team in the organization.

## What are the benefits of adopting Azure landing zones?

Whilst Azure makes it very easy to get started in the Cloud, things can quickly get out of hand. Costs can quickly spiral, resources can be deployed in an insecure way and adoption can be difficult to scale and support.

Adopting brings the following benefits to your organisation:

**Standardisation**  
Azure Landing Zones establish a standardised approach. By following best practices, organisations reduce operational complexities and ensure consistency.

**Confidence in Cloud Adoption**  
With a well-defined landing zone, organisations gain confidence. They can migrate, modernise, and innovate while adhering to industry standards. ‍

**Operational Efficiency**  
Consolidating shared services in platform landing zones improves efficiency. Centralised management streamlines tasks like identity management and governance. ‍

**Security and Compliance**  
Azure Landing Zones enforce security controls. Organizations apply consistent measures across their environment.

## What does it look like in practice?
![Architecture](/assets/img/landing-zone-architecture.png "Architecture")

**Enterprise enrollment**  
This represents the commercial relationship between Microsoft and how your organisation uses Azure. It provides a billing foundation for your subscriptions and how your digital estate is administered.

**Management group and subscription organisation**  
This shows the suggested hierarchy of management groups and subscriptions.

**Management subscription**  
This contains shared services for management, for example, Dashboards, Automation Accounts and Log Analytics workspaces.‍

**Identity subscription**  
This relates to controls and processes used to ensure access is secure and compliant.‍

**Connectivity subscription**  
This contains shared services for connectivity e.g. On-premise connectivity, network virtual appliances, inter-region routing, and hybrid DNS.‍

**Corp subscriptions**  
Landing zones with services/resources that need access to internal services (intranet).

**Online subscriptions**  
Landing zones with services/resources that do not need access to internal services (internet).

## How do I implement landing zones?

**Do It Yourself**  
Design your landing zones from scratch, considering your organisation’s unique requirements.

**Pre-Built Solutions**  
Microsoft offers various Azure Landing Zone Accelerators. The accelerators provide opinionated target architectures, templates, and scripts.

**Bring in help**  
I work with organizations to understand the requirements and implement the right solution to accelerate the journey to the Cloud. The solutions are mostly built on Microsoft’s Cloud Adoption Framework.

## Summary
Azure Landing Zones provide a secure, scalable foundation for cloud deployments, adhering to best practices in areas like identity management, network architecture, and security. By adopting Azure Landing Zones, organizations can standardize their cloud environments, ensure operational efficiency, and maintain compliance with security and governance requirements. Whether designing custom landing zones or leveraging Microsoft's pre-built solutions, these foundational environments help organizations accelerate their cloud journey while maintaining control and confidence in their infrastructure.