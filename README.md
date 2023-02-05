# Microsoft Virtual Desktop - Engagement Guideline

The goal of this article is to provide a guideline on assessment of customer needs, requirements
and architecture for virtual desktop projects based on Microsoft Virtual Desktop (VDI) technologies.
Target audience is pre-sales team, so that the team can accelerate Virtual Desktop based projects
and understand the project technical directions quickly.

## Overview

Microsoft provides several technology options for VDI implementation.
Which technology to use?
It depends on the specific use case, customer size, workload size, team size and operations capabilities.

### Microsoft Virtual Desktop options

- Desktop as a Service (DaaS) - A complete service that securely streams
  your personalized Windows desktop, apps, settings, and content from the Microsoft cloud, to any device
  - Windows 365 Cloud PC (DaaS) - <https://www.microsoft.com/en-us/windows-365>
  - Microsoft Dev Box (DaaS) - Dev workstation in the cloud - <https://azure.microsoft.com/en-us/products/dev-box>
- Azure Virtual Desktop (AVD) - Cloud VDI platform that delivers hosted desktops and apps with maximum flexibility.
  This option is typically used (not required but recommended) with third party addon. Pure AVD without addons is harder to manage for larger environments.
  - AVD with VMWare control plane
  - AVD with Citrix control plane
  - AVD with Nerdio or other third party control plane management tool
- Traditional VDI On-Prem/IaaS - RDS/Citrix/VMware - NOT considered here as it's NOT considered as modern desktop implementation path.

Generally, rule of thumb for choice is DaaS option based on Windows 365 Cloud PC or Microsoft Dev Box.
This should be considered as the primary choice unless requirements guide us into other options.

If DaaS solution does NOT fit into the requirements then consider AVD with VMWare or Citrix control plane.
This makes especially sense for customers who have a team which is familiar with VMWare/Citrix VDI solution already
and they would like to expand solution into the cloud.

Another great option is to use AVD with Nerdio product which will provide AVD flexibility plus simplicity on the management
of the AVD platform via Nerdio tool with great tooling for cost savings.
It is a very good solution for greenfield deployments and/or migrations from alternative products.

### Microsoft Virtual Desktop in a Cloud philosophy

- Designed for connecting from everywhere (you can still limit access based on region, managed/approved device, approved identity, etc.)
- Designed for AAD based cloud identity with Conditional access, MFA
- Manage desktop with classic tools like SCCM or with modern cloud tools like Microsoft Endpoint Manager and/or Defender for Endpoint

## Windows 365 Cloud PC
