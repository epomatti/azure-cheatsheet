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

|          | V1 | V2 FileStorage <br/> (Premium) | BlobStorage <br/> (Premium) | V2 Standard | 
| -------- | :-------------:| :---------------:|:----:| :---: | 
| **Access Tier (Hot, Cool)**    | - | -| ✔️ | ✔️ |
| **Support File Shares**    | - | ✔️ | - | ✔️ | 
| **Max Redundancy**    |  | ZRS | ZRS |  | 
| **Support Transaction Optimized**    |  |  |  |  | 


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
- **Traffic Analytics** provides insights over data collected by Network Watcher services, such as NSG Flow Logs

## Monitor

- Security logs tables for VMs:
  - Windows - Events
  - Linux - Syslog

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

## Virtual WAN

- **Basic** - Supports only VPN Gateways
- **Standard** - Required for ExpressRoute

## Azure Functions

|          | Consumption <br/> (Serverless) | Premium | Dedicated <br/> (App Service Plan)  | ASE |
| -------- | :-------------:| :---------------:|:----:|:----:|
| **Virtual Network**    | - | ✔️| - | ✔️ |


## Logic Apps

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

IT Service Management, for example running on-premises, can me integrated with Azure Monitor to receive alerts of service health by configuring an ITSM Connector service group.