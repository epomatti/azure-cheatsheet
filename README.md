# AZ-305 Cheatsheet

Collection of relevant AZ-305 notes.

## Azure AD Identity Management

- Able to create access reviews
- Within access reviews, to send periodic review emails to managers
- Within access reviews, Automatically revokes access from users if manager doesn't verify the permissions

## Privileged Access Management (PIM)

- Create eligible and active permissions
- Both Azure AD and Azure permissions
- Just-in-Time (JIT)

## Storage

### Storage Account V2

- 

## Azure AD Application Proxy

[How it works](https://docs.microsoft.com/en-us/azure/active-directory/app-proxy/application-proxy#how-application-proxy-works)

- AAD Application Proxy allows users to connect to an on-premises app without VPN
- Azure AD Enterprise Application is required **first** - the configuration of the Application Proxy Service is done per app
- On-premises Application Proxy Connector is required (it runs on Windows on-prem)
  - The connector may authenticate to the on-premises Active Directory