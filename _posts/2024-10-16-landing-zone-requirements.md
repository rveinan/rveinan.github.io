---
title: "Mastering Azure Landing Zones: Overcoming challenges and meeting key requirements"
date: 2024-10-16 18:00:00 +0100
description: "Gain understanding of the essential challenges and critical requirements for implementing Azure Landing Zones effectively."
categories: [Azure]
tags:
  [
    Microsoft Azure,
    Landing Zones
  ]
image:
  path: /assets/img/challenges.jpg
  src: /assets/img/challenges.jpg
---

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

## Key requirements for landing zones

### Type of Landing Zone
When defining landing zones, organizations need to consider the types based on their specific use cases:

**Online**  
These are the primary environments for most cloud applications and resources. They are designed for services that do not require stringent security measures beyond standard access controls and do not need connections to internal intranet services.

**Corp**  
This type is necessary for services and resources requiring access to intranet-based services that necessitate VPN connectivity. Corp Landing Zones come with enhanced security protocols, such as the use of Private Endpoints and restrictions ensuring that all services are accessed only through API Management or a Web Application Firewall.

### Policies
Implementing Azure Policies is crucial for defining and enforcing rules and standards across Azure resources within landing zones. These policies ensure that deployed resources comply with organizational best practices for security, performance, and compliance. Policies can be categorized as follows:

**Policies** are individual rules or security controls that dictate specific requirements.

**Initiatives** are groupings of related policies that represent overarching guidelines within the organization.

Each policy has defined effects that determine actions when requirements are unmet:  

**Audit** reports resources that do not meet the requirements of the relevant policy but does not restrict any actions or deployments beyond this. However, this does not mean that the policy is merely advisory; it is still a requirement within the organization.

**Deny** restricts the creation or updating of resources that do not meet the requirements of the relevant policy.

### Essential components of a Landing Zone
A well-structured landing zone should provide a unique Azure subscription for each environment, with access managed through defined security groups. Responsibilities include adding members to these groups or approving access requests as necessary. Each landing zone should include the following resource types:

**Tags** that should provide required tags on the subscription.

**Managed Identity + federation and access** for workload deployments (IaC/GitHub)

**RBAC** or ***Role based access control***, for access to the landing zone.

**Security** that should include Defender Princing Tier and Security Contact.

**Budget** that can be used for monthly budget(s) on Azure subscriptions.

**VNet** that is additional for ***Corp*** landing zones and provides peering to the network hub (Virtual Wan) for connection to the corporate network.

## Summary
Azure Landing Zones are essential for organizations aiming to establish a structured, secure, and scalable cloud environment. However, implementing them comes with challenges, including inconsistent resource management, compliance issues, and the complexities of maintaining up-to-date configurations. To successfully navigate these challenges, organizations must define clear requirements for their landing zones, such as choosing the appropriate type (Online or Corp), establishing robust policies, and ensuring essential components like managed identities, RBAC, and budgets are in place. By addressing these challenges and meeting the outlined requirements, organizations can effectively leverage Azure Landing Zones to facilitate their cloud journey while maintaining control over governance and security.