---
title: "Azure Landing Zones"
date: 2024-10-21 17:00:00 +0100
description: "What is a landing zone?"
categories: [Azure]
tags:
  [
    Microsoft Azure,
    Landing Zones
  ]
image:
  path: /assets/img/azure-landing-zone.jpeg
  src: /assets/img/azure-landing-zone.jpeg
---
# What is an Azure landing zone?

A landing zone is an area or a container where workloads (services) can operate. The landing zone is subject to a set of policies and restrictions that ensure everything operate within organizational guidelines and directives.

You can compare a landing zone to a room in a house. Each room in the house is unique to its purpose, just like products will be unique to each product team.

A landing zone in Azure is a set of predefined resources and services optimized to support cloud-based workloads. It is used to accelerate the migration or development of cloud applications by providing a standardized, secure, and scalable infrastructure. A landing zone can be customized based on various needs and scenarios, depending on factors such as security requirements, performance goals, cost control, and governance models.

### Types of landing zones

**Online**
This landing zone type is the primary zone for most cloud applications/resources. It covers services that do not require more protection than normal access control and do not need access to internal services that require intranet access.

**Corp**
Services/resources that need access to intranet-based services, which require VPN access, should be placed in this landing zone type. This zone has more stringent security requirements than the Online landing zone. For example, it may include the use of Private Endpoints, or restrictions ensuring that all services can only be accessed through either API Management or a Web Firewall.

## Requirements

When you receive a new landing zone, you must adhere to a set of policies and guidelines associated with that landing zone. An overview of the policies that will affect you in your new landing zone can be found in the Azure portal.

**Policy**
Azure Policy is a tool used to define and enforce rules and standards for Azure resources. In the context of a landing zone, an Azure Policy ensures that the resources created within the zone follow best practices for security, performance, cost, and compliance. For example, an Azure Policy might control which types of virtual machines can be created in a landing zone or require that all resources have a specific tag or role. Policies are divided into both policies and initiatives:

***Policies*** are individual restrictions or security controls.

***Initiatives*** are simply a grouping of a set of policies and represent the guidelines in the organization.

Each policy has an effect that determines what happens if the requirements of the policy are not met. The effects that are used are:

***Audit***
This effect reports resources that do not meet the requirements of the relevant policy but does not restrict any actions or deployments beyond this. However, this does not mean that the policy is merely advisory; it is still a requirement within the organization.

***Deny*** 
This effect restricts the creation or updating of resources that do not meet the requirements of the relevant policy.

## Ordering a landing zone

This is typically done through GitHub. The system owner (or similar) can place an order for a new landing zone. It is a requirement that you have already considered the type of landing zone, as it determines the different Azure policies applied during the creation of the landing zone.

***Considerations when choosing the type of landing zone***

Do you need access to services that are not already available through published services in API Management (APIM)?
- Corp

Do the services only have dependencies to online services?
- Online

## What should the landing zone include?
**Azure**
The landing zone will provide a new unique subscription in Azure for each environment defined with access distributed to the relevant security groups specified in the landing zone order. Members of these security groups will automatically gain access to their new landing zone. The landing zone owner is responsible for adding members to their respective security groups or approving access requests if MyAccess is in use.The following resource types should be created per landing zone in Azure based on the selected landing zone type:

- Tags (Required tags on the subscription)
- Managed Identity + federation and access (Identity for workloads (IaC/GitHub))
- RBAC (Role based access for the landing zone)
- Security (Defender Princing Tier and Security Contact)
- Budget (Can be used for monthly budget on Azure subscriptions)
- VNet (additional for corp) with peering to the network hub (Virtual Wan) for connection to the corporate network

**GitHub**
The landing zone will provide a new unique repository (code library) in GitHub with access distributed to your landing zone team. In this team, GitHub members can be added for access to their repository. The following will be created per landing zone in GitHub:

- Repository (Unique code library for the landing zone)
- Security (Branch protection)
- Team (Unique GitHub team for the landing zone)
- Configuration for Azure (IaC deployments)
- Examples of IaC Workloads	(Workload deployment)