---
title: "Manage access to landing zones"
date: 2024-10-17 18:00:00 +0100
description: "Discover key concepts like principals, roles, permissions, and scope and the use of Privileged Identity Management."

categories: [Azure]
tags:
  [
    Microsoft Azure,
    Landing Zone Access,
    Access Control
  ]
image:
  path: /assets/img/access.jpg
  src: /assets/img/access.jpg
---

## Introduction

Access to landing zones can be managed using Azure RBAC (Role-Based Access Control). The way you control access to resources by using Azure RBAC is through role assignments, which can be broken down into the following:

**Role assignment = Principal (Who) + Permission (What) + Scope (Where)**  

### Principal

A principal is an object representing a user, group, service principal, or managed identity that requests access to Azure resources.

### Role

A role definition is a collection of permissions, commonly referred to as a role. A role definition specifies the actions that can be performed, such as read, write, and delete. Roles can range from high-level, like Owner, to specific, like Developer.

### Permissions

For permissions, the scope refers to the set of resources the permissions apply to. When assigning a role, actions can be restricted by defining the scope. Example below:

| **Permission**            | **Description**                                                                                    |
|---------------------------|-------------------------------------------------------------------------------------------------   |
| **Cost Management Contributor** | Can view costs and manage cost configuration (e.g., budgets and alerts)                      |
| **Owner**                  | Provides full access to manage all resources and assign RBAC roles  |
| **Reader**                 | Can view all resources but cannot make changes                                                    |
| **Contributor**            | Provides full access to manage all resources, but not assign RBAC roles  |
| **Key Vault Administrator**| Grants access to Key Vault and objects within it (keys, secrets, certificates)       |

### Group

A group is a principal that requests access to Azure resources. The group should include all members who need access to their landing zone(s) in Azure.

You can use role groups to differentiate between permanent (static) access and available PIM (Privileged Identity Management) assignments. PIM provides time-based and approval-based role activation to reduce the risk of unnecessary access permissions to Azure resources.

## Access Management

Example of landing zone access with security groups:

| **Corp and Online**         | **Role** | **Permissions** |
|-----------------------------|----------|-----------------|
| **Owner**                   | Cost Management Contributor | SG-Owner |
| **Admin**                   | [PIM]: Owner [Permanent]: Reader | SG-Admin |
| **Developer**               | [PIM]: Contributor [PIM]: Key Vault Administrator [Permanent]: Reader | SG-Developer |