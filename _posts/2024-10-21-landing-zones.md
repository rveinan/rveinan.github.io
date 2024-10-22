---
title: "Azure Landing Zones"
date: 2024-10-21 17:00:00 +0100
description: "Discover how Azure Landing Zones establish a secure, scalable foundation for deploying workloads in Microsoft Azure, enhancing your enterprise's cloud adoption journey with confidence"
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

## What should your organization require for landing zones?

### The type of landing zone

**Online**  
This landing zone type is the primary zone for most cloud applications/resources. It covers services that do not require more protection than normal access control and do not need access to internal services that require intranet access.

**Corp**  
Services/resources that need access to intranet-based services, which require VPN access, should be placed in this landing zone type. This zone has more stringent security requirements than the Online landing zone. For example, it may include the use of Private Endpoints, or restrictions ensuring that all services can only be accessed through either API Management or a Web Firewall.

### Policies
Azure Policy is a tool used to define and enforce rules and standards for Azure resources. In the context of a landing zone, an Azure Policy ensures that the resources created within the zone follow best practices for security, performance, cost, and compliance. For example, an Azure Policy might control which types of virtual machines can be created in a landing zone or require that all resources have a specific tag or role. Policies are divided into both policies and initiatives:

**Policies** are individual restrictions or security controls.

**Initiatives** are simply a grouping of a set of policies and represent the guidelines in the organization.

Each policy has an effect that determines what happens if the requirements of the policy are not met. The effects that should be used are:

**Audit**  
This effect reports resources that do not meet the requirements of the relevant policy but does not restrict any actions or deployments beyond this. However, this does not mean that the policy is merely advisory; it is still a requirement within the organization.

**Deny**  
This effect restricts the creation or updating of resources that do not meet the requirements of the relevant policy.

## What should the landing zone provide?
The landing zone should provide a new unique subscription in Azure for each environment defined with access distributed to the relevant security groups specified in the landing zone order. Members of these security groups will automatically gain access to their new landing zone. The landing zone owner is responsible for adding members to their respective security groups or approving access requests if MyAccess is in use.The following resource types should be created per landing zone in Azure based on the selected landing zone type:

**Tags**  
Required tags on the subscription.

**Managed Identity + federation and access**  
Identity for workloads (IaC/GitHub).

**RBAC**  
Role based access for the landing zone.

**Security**  
Defender Princing Tier and Security Contact.

**Budget**  
Can be used for monthly budget on Azure subscriptions.

**VNet**  
This should be additional for Corp landing zones and provide peering to the network hub (Virtual Wan) for connection to the corporate network.

## What are common challenges with landing zones?

**Lack of consistency in resource naming, scaling, and role-based access control**  
This can lead to confusion and errors when managing resources.

**Spending more time on deploying and managing resources**  
This can be due to the complexity of the deployment process and the need to manage multiple environments.

**Non-compliance**  
Regulatory compliance is a critical concern for many organisations. Ensuring that Azure Landing Zones are compliant with regulatory requirements can be a challenge.

**Keeping Azure Landing Zones up-to-date**  
Maintaining Azure Landing Zones can be complex, depending on how they are deployed.

**Choosing the right solution**  
E.g. the Azure landing zone accelerator can tend to end up causing trouble due to things like configuration drift.

## How do I implement landing zones?

**Do It Yourself**  
Design your landing zones from scratch, considering your organisation’s unique requirements.

**Pre-Built Solutions**  
Microsoft offers various Azure Landing Zone Accelerators. The accelerators provide opinionated target architectures, templates, and scripts.

**Bring in help**  
I work with organizations to understand the requirements and implement the right solution to accelerate the journey to the Cloud. The solutions are mostly built on Microsoft’s Cloud Adoption Framework.