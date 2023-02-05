# Microsoft Virtual Desktop - Engagement Guideline

The goal of this article is to provide a guideline on assessment of customer needs, requirements
and architecture for virtual desktop projects based on Microsoft Virtual Desktop (VDI) technologies.
Target audience is pre-sales team, so that the team can accelerate Virtual Desktop
value based delivery and understand the project technical directions quickly.

## Overview

Microsoft provides several technology options for VDI implementations.
Which technology to use?
It depends on the specific business benefits, use case, customer size, workload size, team size and operations capabilities.

### Modern Microsoft Virtual Desktop in a Cloud benefits

Modern Virtual Desktop is designed / ideal for following use cases:

- Elastic workforce
  - Mergers and acquisition
  - Short-term employees
  - Contractors and partners
- Remote employees
  - Bring your own device (BYOD) and mobile
  - Call centers
  - Branch workers
- Specialized workloads
  - Design and engineering
  - Legacy apps
  - Software dev test
  - Data science / Machine learning projects (quickly calculate models and stop resources)
  - Enable GPU accelerated app rendering and encoding

Business benefits of modern Virtual Desktop - cloud based solution:

- Access your desktop and applications from anywhere (Productivity) - Desktop is available worldwide. Enable secure remote work. Provide employees the best virtualized experience with the only solution fully optimized for Windows 11 and Microsoft 365.
- Bring your own device (BYOD) / Reduce Enterprise HW (Costs) - Access your desktop and applications over the internet from light devices using an Azure Virtual Desktop client such as Windows, Mac, iOS, Android, or HTML5.
- Run multiple concurrent user sessions (Costs) - Choose the right Azure virtual machine (VM) to optimize performance and leverage the Windows 10 and Windows 11 multi-session advantage on Azure.
- Leverage the seamless Microsoft Teams and Microsoft Office experience (Productivity) - Provide employees with the same experience they'd have on a local desktop or laptop - whether they're managing their inbox with Outlook, sharing files in OneDrive, or collaborating with colleagues on Microsoft Teams.
- Deploy and scale in minutes (Costs) - Simplify deployment and management of your infrastructure and scale quickly based on your business needs.
- Reduce cost using existing licenses (Costs) - Use existing eligible licenses to reduce costs with a modern cloud-based virtual desktop infrastructure (VDI), and pay only for what you use.

Technological benefits and details:

- Managed backend by Microsoft helps reduce the costs and time spent managing on-premises infrastructure / DMZ
- Designed for connecting from everywhere (you can still limit access based on region, managed/approved device, approved identity, etc.)
- Designed for Azure Active Directory based cloud identity with Conditional access and Multi-Factor Authentication to secure your virtual desktops
- Manage desktop with classic tools like SCCM or with modern cloud tools like Microsoft Endpoint Manager and/or Defender for Endpoint
- Use existing Windows and Microsoft 365 licenses to access Windows 11 and Windows 10 and Microsoft Office
- Run multiple desktop sessions on a single VM with exclusive Windows 11 and Windows 10 multi-session​

#### Resources

- <https://azure.microsoft.com/en-us/products/virtual-desktop/>

### Microsoft Virtual Desktop options

- Desktop as a Service (DaaS) - A complete service that securely streams
  your personalized Windows desktop, apps, settings, and content from the Microsoft cloud, to any device
  - Windows 365 Cloud PC (DaaS) - <https://www.microsoft.com/en-us/windows-365>
  - Microsoft Dev Box (DaaS) - Dev workstation in the cloud - <https://azure.microsoft.com/en-us/products/dev-box>
- Azure Virtual Desktop (AVD) - Cloud VDI platform that delivers hosted desktops and apps with maximum flexibility.
  This option is typically used (not required but recommended) with partner VDI solutions. Pure AVD without partner addons is harder to manage for larger environments.
  - AVD with VMWare control plane
  - AVD with Citrix control plane
  - AVD with Nerdio or other third party control plane management tool
- Traditional VDI On-Prem/IaaS - RDS/Citrix/VMware - NOT considered here as it's NOT considered as modern desktop implementation path.

Generally, rule of thumb for choice is DaaS option based on Windows 365 Cloud PC or Microsoft Dev Box.
This should be considered as the primary choice unless requirements guide us into other options.

If DaaS solution does NOT fit into the requirements then consider AVD with VMWare or Citrix control plane.
This makes especially sense for customers who have a team which is familiar with VMWare/Citrix VDI solution already
and they would like to expand solution into the cloud (brownfield deployment).

Another great option is to use AVD with Nerdio product which will provide AVD flexibility plus simplicity on the management
of the AVD platform via Nerdio tool with great tooling for cost savings.
It is a very good solution for greenfield deployments and/or migrations from alternative products.

## Windows 365 Cloud PC

Windows 365 Enterprise is for organizations that want to manage their Cloud PCs with Microsoft Endpoint Manager and take advantage of integrations with other Microsoft services, including Azure Active Directory (Azure AD) and Microsoft Defender for Endpoint. Windows 365 Enterprise has no license limit.

To use Windows 365 Enterprise, each user must be licensed for Windows 11 Enterprise or Windows 10 Enterprise, Endpoint Manager, and Azure AD P1. In addition to being available independently, these licenses are included in Microsoft 365 F3, Microsoft 365 E3, Microsoft 365 E5, Microsoft 365 A3, Microsoft 365 A5, Microsoft 365 Business Premium, and Microsoft 365 Education Student Use Benefit subscriptions.

Business, Technical features and limitations:

- Windows 365 is Desktop as a Service (DaaS) solution.
- It's ideal for customers looking for managed service with always ready desktop.
- It's dedicated (personal) Windows 10/11 desktop (only) running 24x7 with flat cost, predictable, per-user, per-month pricing and O365 license at least E3.
- Optimal for the use cases like Office/Information worker with O365 where customer has no much expertize / none or small Virtual Desktop team.
- Deployed Virtual Desktops can still be part of Enterprise network and desktop can be hardened as needed.
- Custom images are supported.
- Almost all Azure regions are supported and can be used for virtual desktop deployments.
- Deploy, manage & secure via Microsoft Endpoint Manager & Web Portal
- Supports Hybrid Azure Active Directory or Azure Active Directory Join.

### Qualifying questions for Windows 365

- Do you have any VDI expertise? Do you want to invest in up-skilling/have a partner manage your VDI? If no, Windows 365 is excellent option. Windows 365 is a DaaS solution and doesn't need VDI expertise to deploy and manage.
- Do you currently use Microsoft Endpoint Manager (or Intune)? If yes, Windows 365 can be good option.
- Do you have existing eligible Windows/M365 license? Typically E3/E5? If yes, Windows 365 can be good option.
- Do you need predictable fixed per user, per month pricing? If yes, Windows 365 can be good option.
- Windows 365 offers limited number of SKUs. See here: <https://www.microsoft.com/en-us/windows-365/enterprise/configure>. Do you think it fits into the requirements? If yes, Windows 365 can be good option.
- Windows 365 is available over Microsoft managed public endpoint only (To support access desktop from anywhere). Do you think it fits into the requirements? If yes, Windows 365 can be good option.

### Resources

- <https://www.microsoft.com/en-us/windows-365/faq>
- <https://www.microsoft.com/en-us/windows-365/enterprise/configure>
