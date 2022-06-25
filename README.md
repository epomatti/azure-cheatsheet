# AZ-305 Cheatsheet

Collection of relevant AZ-305 notes.

## Azure AD Identity Management

- Able to create access reviews
- Within access reviews, to send periodic review emails to managers
- Within access reviews, Automatically revokes access from users if manager doesn't verify the permissions
- Users can also report for their access reviews
- Users are removed when report that they don't need the permission, or if they do not respond as well

## Privileged Access Management (PIM)

- Create eligible and active permissions
- Both Azure AD and Azure permissions
- Just-in-Time (JIT)

## Storage Accounts

### SKUs

|          | V1 | V2 FileStorage <br/> (Premium) | BlobStorage <br/> (Premium) | V2 Standard | 
| -------- | :-------------:| :---------------:|:----:| :---: | 
| **Access Tier (Hot, Cool)**    | - | -| ✔️ | ✔️ |
| **Support File Shares**    | - | ✔️ | - | ✔️ | 
| **Max Redundancy**    |  | ZRS | ZRS | RA-GRS | 
| **Support Transaction Optimized**    | - | - | - | ✔️ (Files) | 
| **Immutability**    |  | - | ✔️ | ✔️ | 

### Access Tiers

- **Hot** - Optimized for data accessed frequently
- **Cool tier** - Minimum o 30 days
- **Archive** - Minimum of 180 days


## Azure AD Application Proxy

[How it works](https://docs.microsoft.com/en-us/azure/active-directory/app-proxy/application-proxy#how-application-proxy-works)

- AAD Application Proxy allows users to connect to an on-premises app without VPN
- Azure AD Enterprise Application is required **first** - the configuration of the Application Proxy Service is done per app
- On-premises Application Proxy Connector is required (it runs on Windows on-prem)
  - The connector may authenticate to the on-premises Active Directory

## Databricks

- Premium SKU is required for permissions in the Databricks folders
- Premium SKU is required for Credential Passthrough

## Network Watcher

- **IP Flow verify** will establish logical verification of connectivity
- **Connection Troubleshoot** will perform real connectivity tests
- **Traffic Analytics** provides insights over data collected by Network Watcher services, such as NSG Flow Logs - Since it uses for example IP Flow underneath, it helps identifying connectivity issues.

## Monitor

### Security Log Tables

- Security logs tables for VMs:
  - Windows - Events
  - Linux - Syslog

### VM Agents

There are [several agents](https://docs.microsoft.com/en-us/azure/azure-monitor/agents/agents-overview) that can send data to Azure Monitor.

## Policies

- Policies can be applied to the following scopes:
  - Management Groups
  - Subscriptions
  - Resources Groups

## SQL Databases

### Tier: vCores


|          | General Purpose <br/> (Standard) | Hyperscale | Business Critical <br/> (Premium) |
| -------- | :-------------:| :---------------:|:----:|
| **Maximum storage size**    | 4 TB | 100 TB| 4 TB |
| **Serverless**    | ✔️ | - | - |
| **Zone Redundant** | ✔️ | ✔️ | ✔️ |
| **Server License** | ✔️ | ✔️ | ✔️ |
| **Read scale-out** | -  |  -  | ✔️ |
| **HA Secondary Replicas** | -  |  ✔️ | - |
| **Geo-redundant Backups** |   |   |  |

### Tier: DTU

|          | Basic | Standard | Premium |
| -------- | :-------------:| :---------------:|:----:|
| **Maximum storage size**    | 2 GB | 1 TB| 4 TB |
| **Serverless**    | - | - | - |
| **Zone Redundant** | - | - | ✔️ |
| **Server License** | - | - | - |
| **Read scale-out** | -  |  -  | ✔️ |
| **HA Secondary Replicas** | -  |  - | - |
| **Geo-redundant Backups** |   |   |  |

### Managed instances

- Up to 16 TB of storage size.
- Support auto-failover.
- Support CLR.
- Support Linked Servers
- Support distributed server-side transactions using Transact-SQL

### Intelligent Performance

SQL offers the following resources to help with performance:

- **Performance recommendations** - Recommendations:  Optimize the layout of non-clustered indexes, Fix database schema issues, fix database parameterization issues.
- **Query Performance Insight** - Lists for top long running queries.
- **Automatic Tuning** - Azure SQL Database built-in intelligence automatically tunes your databases to optimize performance. Click here to learn more about automatic tuning.

### Azure SQL Analytics

Operations Management Suite (OMS) is a management offering which provides monitoring for Azure Resources through the Log Analytics service. Log Analytics enables users to collect, correlate and visualize structured and unstructured data. Through the out of the box solutions available in OMS Log Analytics, users can easily monitor and receive notifications on the health of their Azure Resources such as SQL Azure.

### Data Security Operations

- **Always Encrypted** - Encrypt entire columns and allow only the application access it
- **Dynamic Data Masking** - Masks parts of sensitive data and allow, allowing for role configuration.
- **Transparent Data Encryption** - Is the encryption at storage level of the disks

## Virtual WAN

- **Basic** - Supports only VPN Gateways
- **Standard** - Required for ExpressRoute

## Azure Functions

### SKUs

|          | Consumption <br/> (Serverless) | Premium | Dedicated <br/> (App Service Plan)  | ASE |
| -------- | :-------------:| :---------------:|:----:|:----:|
| **Virtual Network**    | - | ✔️| - | ✔️ |

### SendGrid

Azure Functions has SendGrid connectors for emails.

## Logic Apps

### Data Gateway + On-prem SQL Server

It is possible to connect Logic Apps to an On-premies SQL Server by using an On-premises Data Gateway and a connection gateway resource.

## API Management (APIM)

|          | Consumption <br/> (Serverless) | Basic | Standard | Premium |
| -------- | :-------------:| :---------------:|:----:|:----:|
| **Multiple custom domains**    | - | -| - | ✔️ |
| **Availability zone support**    | - | -| - | ✔️ |
| **Virtual network support**    | - | -| - | ✔️ |
| **Multi-region deployment**    | - | -| - | ✔️ |

## Budgets

To take action with budgets, create a Budget and associate to an Action Group from (Azure Monitor) Alert.

If you wish for example, to turn off resources, it would be created with an Automation Runbook.


## Log Analytics

Maximum retention period is 730 days (or 24 months / 2 years).


## IT Service Management (ITSM)

IT Service Management, for example running on-premises, can me integrated with Azure Monitor to receive alerts of service health by configuring an ITSM Connector action group.

## Analysis Services

PaaS solution to provide enterprise-grade data models.

Combine from multiple data-sources into a single tabular data model.

## Microsoft Sentinel

See and stop threats before they cause harm, with SIEM reinvented for a modern world. Microsoft Sentinel is your birds-eye view across the enterprise.

## Active Directory (AD)

### Hybrid Identity

- **Synchronized identity (passthrough credentials)** allow authentication on Azure AD with on-premises credentials.
- **Federated identity** allow for authentication by on-premises domain controller.

### Microsoft Office 365 IdFix

IdFix is used to perform discovery and remediation of identity objects and their attributes in an on-premises Active Directory environment in preparation for migration to Azure Active Directory.

### Hybrid Identity Cloud Login

From [compare AD Auth methods](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/choose-ad-authn#comparing-methods):

- **Password Hash synchronization + Seamless SSO** => Authentication happens in the Cloud
- **Pass-through authentication + Seamless SSO** => Authentication happens in the cloud AFTER on premises
- **Federation with AD FS** => On-Premises

### Seamless Sign-On

Seamless Sign-on is compatible with Pass-through and also Password-hash synchronization.

### Graph API permissions

To give an app delegated permissions, such as managing access reviews or key vault, create an App on Azure AD admin center, and apply API permissions in the app for Graph API.

### Just in Time

Used to have access to the VMs, but not to manage them using the portal. What would be PIM.

## Blueprints

Only blueprints can restrict Subscription owner permissions, such as deleting resources groups via Blueprint lock.

## Data Factory

### Integration Runtime

The Integration Runtime (IR) is the compute infrastructure used by Azure Data Factory and Azure Synapse pipelines to provide the following data integration capabilities across different network environments.

Example: Connect data from within a VM.

With that you should be able to just create a pipeline directly if import files.

## Virtual Machines (VM)

### SQL Server Managed Disks

When running SQL Server on VMs, prefer the following configuration:

- **Logs Disk** - No Cache
- **Data Disk** - Read-Only Cache

### Disk Encryption

When encrypting Managed Disks on VMs:

- **Disk Encryption**

It will allow for transparent encryption, and with custom keys if needed (via Key Vault).

Other options:

- Client-side Encryption - This will not apply to VM disks
- Storage Service Encryption - This would be for unmanaged disks
- Encryption File Systems (EFS) - This is for Windows only
