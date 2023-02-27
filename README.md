# Microsoft Virtual Desktop - Engagement Guideline

The goal of this article is to provide a guideline on assessment of customer needs, requirements
and architecture for virtual desktop projects based on Microsoft Virtual Desktop (VDI) technologies.
Target audience is pre-sales team and architects, so that the team can accelerate Virtual Desktop
value-based delivery and understand the project needs and technical directions quickly.

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
  - Bring your own device (BYOD) and mobile.
  - Call centers
  - Branch workers
- Specialized workloads
  - Design and engineering
  - Remote management E.g., Jump hosts.
  - Legacy apps
  - Software dev test
  - Data science / Machine learning projects (quickly pre-calculate models and stop resources)
  - Enable GPU accelerated app rendering and encoding.

Why Virtual Desktop in Cloud? Business benefits of modern Virtual Desktop:

- Benefits from Productivity perspective
  - Access your desktop and applications from anywhere - Desktop is available worldwide. Enable secure remote work. Provide employees the best virtualized experience with the only solution fully optimized for Windows 11 and Microsoft 365.
  - Leverage the seamless Microsoft Teams and Microsoft Office experience - Provide employees with the same experience they would have on a local desktop or laptop - whether they're managing their inbox with Outlook, sharing files in OneDrive, or collaborating with colleagues on Microsoft Teams.

- Benefits from Costs perspective
  - Bring your own device (BYOD) / Reduce Enterprise HW/Devices - Access your desktop and applications over the internet from light devices using an Azure Virtual Desktop client such as Windows, Mac, iOS, Android, or HTML5.
  - Consolidate/Run multiple concurrent user sessions - Choose the right Azure virtual machine (VM) to optimize performance and leverage the Windows 10 and Windows 11 multi-session advantage on Azure.
  - Migrate from peak capacity costs on-premises to actual consumption-based. Advanced power management and provisioning scale back idle VMs to save costs.
  - Simplify deployment and management of your infrastructure and scale quickly based on your business needs.
  - Reduce cost using existing licenses E.g., E3/E5 - Use existing eligible licenses to reduce costs with a modern cloud-based virtual desktop infrastructure (VDI) and pay only for what you use.
  - No need to manage gateways, brokers, databases, or any other plumbing infrastructure.
  - Save with Linux-based pricing for Windows Server workloads with AVD - Hybrid Use Benefit.
  - Migrate users with M365 license from Windows Server to Windows 10 multi-session to save on an RDS license - This can remove RDS CAL requirement. Standard price is ~$17 per user per month - this will be a cost saving for you per user.

- Benefits from Technology perspective
  - Connect from everywhere (you can still limit access based on region, managed/approved device, approved identity, etc.)
  - Secure with Azure Active Directory based cloud identity with Conditional access and Multi-Factor Authentication to secure your virtual desktops
  - Use existing Windows and Microsoft 365 licenses to access Windows 11 and Windows 10 and Microsoft Office
  - Scale from Windows 10/11 Virtual Desktop to Azure exclusive Windows 10/11 multi-session
  - Extend your compliance, security, and business requirements to the cloud
  - Manage on-premises and cloud workloads side-by-side. Enable hybrid environments Leverage existing on-premises solutions together with Virtual Desktop in Azure
  - Benefit from managed backend by Microsoft to reduce the costs and time spent managing on-premises infrastructure / DMZ. No need to manage gateways, brokers or any other infrastructure. Compute and storage management moves to cloud.
  - Manage desktops with classic tools like SCCM or with modern cloud tools like Microsoft Endpoint Manager and/or Defender for Endpoint. Updates, patches, monitoring, and other management are easier.

#### Resources

- <https://azure.microsoft.com/en-us/products/virtual-desktop/>

### Microsoft Virtual Desktop options

- Desktop as a Service (DaaS) - A complete service that securely streams
  your personalized Windows desktop, apps, settings, and content from the Microsoft cloud, to any device
  - Windows 365 Cloud PC (DaaS) - <https://www.microsoft.com/en-us/windows-365>
  - Microsoft Dev Box (DaaS) - Dev workstation in the cloud - <https://azure.microsoft.com/en-us/products/dev-box>
- Azure Virtual Desktop (AVD) - Cloud VDI platform that delivers hosted desktops and apps with maximum flexibility.
  This option is typically used (not required but recommended) with partner VDI solutions. Pure AVD without partner addons is harder to manage for larger environments.
  - AVD with Azure control plane - <https://azure.microsoft.com/en-us/products/virtual-desktop>
  - AVD with VMWare control plane - <https://azure.microsoft.com/en-us/services/virtual-desktop/vmware-horizon-cloud>
  - AVD with Citrix control plane - <https://azure.microsoft.com/en-us/services/virtual-desktop/citrix-virtual-apps-desktops-for-azure>
  - AVD with Nerdio or other third party control plane management tool - <https://getnerdio.com/>
- Traditional VDI On-Prem/IaaS - RDS/Citrix/VMware - NOT considered here as it's NOT considered as modern desktop implementation path.

Generally, rule of thumb for default choice is DaaS option based on Windows 365 Cloud PC or Microsoft Dev Box.
This should be considered as the primary choice unless requirements guide us into other directions.

If DaaS solution does NOT fit into the requirements then consider AVD with VMWare or Citrix control plane.
This makes especially sense for customers who have a team which is familiar with VMWare/Citrix VDI solution already
and they would like to expand solution into the cloud (brownfield deployment).

Another great option is to use AVD with Nerdio product which will provide AVD flexibility plus simplicity on the management
of the AVD platform via Nerdio tool with great tooling for cost savings.
It is a particularly satisfactory solution for greenfield deployments and/or migrations from alternative products.

## Windows 365 Cloud PC

Windows 365 Enterprise is for organizations that want to manage their Cloud PCs with Microsoft Endpoint Manager and take advantage of integrations with other Microsoft services, including Azure Active Directory (Azure AD) and Microsoft Defender for Endpoint. Windows 365 Enterprise has no license limit.

To use Windows 365 Enterprise, each user must be licensed for Windows 11 Enterprise or Windows 10 Enterprise, Endpoint Manager, and Azure AD P1. In addition to being available independently, these licenses are included in Microsoft 365 F3, Microsoft 365 E3, Microsoft 365 E5, Microsoft 365 A3, Microsoft 365 A5, Microsoft 365 Business Premium, and Microsoft 365 Education Student Use Benefit subscriptions.

Business, Technical features and limitations:

- Windows 365 is Desktop as a Service (DaaS) solution.
- It's ideal for customers looking for managed service with always ready desktop.
- It's dedicated (personal) Windows 10/11 desktop (only) running 24x7 with flat cost for compute, predictable, per-user, per-month pricing and O365 license at least E3.
- Optimal for the use cases like Office/Information worker with O365 where customer has no much expertise / none or small Virtual Desktop team.
- Deployed Virtual Desktops can still be part of Enterprise network and desktop can be hardened as needed.
- Custom images are supported.
- Almost all Azure regions are supported and can be used for virtual desktop deployments.
- Deploy, manage & secure via Microsoft Endpoint Manager & Web Portal
- Supports Hybrid Azure Active Directory or Azure Active Directory Join.
- Set conditional access policies that require users to connect via a compliant device.
- Set multi-factor authentication (MFA) sign-in.

### Qualifying questions for Windows 365

- Do you have any VDI expertise? Do you want to invest in up-skilling/have a partner manage your VDI? If not, Windows 365 is excellent option. Windows 365 is a DaaS solution and does not need VDI expertise to deploy and manage.
- Do you currently use Microsoft Endpoint Manager (or Intune)? If yes, Windows 365 can be good option.
- Do you have existing eligible Windows/M365 license? Typically, E3/E5? If yes, Windows 365 can be a good option.
- Do you need predictable fixed per user, per month pricing? If yes, Windows 365 can be a good option.
- Windows 365 offers a limited number of SKUs. See here: <https://www.microsoft.com/en-us/windows-365/enterprise/configure>. Do you think it fits into the requirements? If yes, Windows 365 can be good option.
- Windows 365 is available over Microsoft managed public endpoint only (To support access desktop from anywhere). Do you think it fits into the requirements? If yes, Windows 365 can be a good option.

### Resources

- <https://www.microsoft.com/en-us/windows-365/faq>
- <https://www.microsoft.com/en-us/windows-365/enterprise/configure>

## Microsoft Dev Box

Microsoft Dev Box is another DaaS offering from Microsoft. Conceptually like Windows 365 with low VDI maintenance overhead.
Key differentiators are pay for use model for compute (no flat cost), self-service, desktop assigned to specific projects with specific set of tools.
Microsoft Dev Box bridges the gap between development teams and IT, bringing control of project resources closer to the development team.
Any use case based on desktop for developers might be good fit for Microsoft Dev Box offering.

Microsoft Dev Box, is a managed service gives you self-service access to high-performance, pre-configured, and ready-to-code cloud-based workstations called dev boxes. You can set up dev boxes (Dev Box images) with the tools, source code, nightly built binaries, and pre-built binaries specific to your project, so you can immediately start work without worrying about workstation configuration and maintenance.
Microsoft Dev Box ensures developers always have the right tools and resources based on project, task, and even role.

Developers stay in control of their Dev Boxes with a developer portal that enables them to create and delete their Dev Boxes for any of their projects. Developers can create Dev Boxes to experiment on a proof-of-concept, keep their projects separate, or even parallelize tasks across multiple Dev Boxes to avoid bogging down their primary environment. For developers working on legacy apps, they can maintain Dev Boxes for older versions of an application to quickly create an environment that can reproduce and diagnose critical customer issues as they emerge.

When building Dev Boxes, dev teams select from a range of SKUs to define the right level of compute for each project and instantly scale up aging physical hardware. Thanks to Azure Active Directory integration, teams can rapidly onboard new team members by assigning them to Azure Active Directory groups that grant access to the Dev Boxes they need for their projects.

At the same time, Microsoft Dev Box ensures unified management, security, and compliance stay in the hands of IT by leveraging Windows 365 to integrate Dev Boxes with Intune and Microsoft Endpoint Manager.

To use Microsoft Dev Box, each user must be licensed for Windows 11 Enterprise or Windows 10 Enterprise, Microsoft Endpoint Manager, and Azure Active Directory P1.

In addition to being available independently, these licenses are included in Microsoft 365 F3, Microsoft 365 E3, Microsoft 365 E5, Microsoft 365 A3, Microsoft 365 A5, Microsoft 365 Business Premium, and Microsoft 365 Education Student Use Benefit subscriptions.

Business, Technical features and limitations:

- Microsoft Dev Box is Desktop as a Service (DaaS) solution.
- It's ideal for end users with development or machine learning needs.
- It's dedicated (personal) Windows 10/11 desktop (only) running on demand with pay as you go cost, O365 license at least E3.
- Optimal for teams which need to have some autonomy and are focused on project developments where developer team doesn't need much expertise on Virtual Desktop management and IT still can have security control.
- Deployed Virtual Desktops can still be part of Enterprise network and desktops can be hardened as needed.
- Custom images are supported.
- Not all Azure regions are supported currently. Check the documentation for target regions <https://azure.microsoft.com/en-us/products/dev-box/#faq>.
- Deploy, manage & secure via Microsoft Endpoint Manager & Web Portal. Dev boxes automatically enroll in Intune. Use Microsoft Endpoint Manager Portal to manage the dev boxes just like any other device on your network. Keep all Windows devices up to date by using Intune’s expedited quality updates to deploy zero-day patches across your organization.
- Supports Hybrid Azure Active Directory or Azure Active Directory Join.
- Set conditional access policies that require users to connect via a compliant device.
- Set multi-factor authentication (MFA) sign-in.
- Configure risk-based sign-in policies for Dev Boxes that access sensitive source code and customer data.
- To keep costs under control, teams can use start/stop schedules to spin up Dev Boxes at the beginning of the day and automatically hibernate them when developers go home.

### Qualifying questions for Microsoft Dev Box

- Check first qualifying questions for Windows 365 option as Microsoft Dev Box has similar setup. Make sure you understand the differentiators described above.
- Do you have a use case which is based on desktop for developers?  If yes, Microsoft Dev Box can be a good option.
- Microsoft Dev Box offers limited number of SKUs. See here: <https://azure.microsoft.com/en-us/pricing/details/dev-box/>. Do you think it fits into the requirements? If yes, Microsoft Dev Box can be a good option.

### Resources

- <https://azure.microsoft.com/en-us/products/dev-box>
- <https://azure.microsoft.com/en-us/pricing/details/dev-box>
- <https://learn.microsoft.com/en-us/azure/dev-box/overview-what-is-microsoft-dev-box>

## AVD with Azure control plane

TODO

## AVD with VMWare/Citrix control plane

Azure AVD with VMWare/Citrix control plane is ideal for organizations which are already using
Citrix and VMware Horizon solution for virtual desktops, and they are happy with it.
Such customers should be encouraged to use existing very mature tools and expand their platform to the cloud
for additional benefits.
In the fact, Azure AVD with VMWare/Citrix control plane can help to accelerate cloud journey for enterprises
which are the beginning with a cloud.
For example, business continuity and disaster recovery scenarios can be great use case for such customers.
Especially, if customer has team which can operate the product in larger deployments with existing skill set,
and customer did other investments into the product.

This is NOT necessarily about migrating control plane to cloud;
this is more about overflowing virtual desktops into the cloud and benefiting from cloud elasticity.
This is hybrid setup which allows renting hardware from the cloud - based on current needs.

Azure AVD with VMWare/Citrix control plane is on the other hand complex enterprise solution with
all pros and cons requiring strong skill set, hybrid architecture mindset,
more traditional tools with full control and flexibility.
Such solution can be harder to setup and manage for NOT skilled teams and greenfield environments.

Business, Technical features and limitations:

- The first option to consider is for existing Citrix and VMware Horizon customers. It provides the same tools (Single pane of glass for all workloads) and reuses the same skill sets for all environments. Maximize existing on-premises investments and skills.
- Hybrid Architecture allows us to manage existing on-premises and cloud workloads side-by-side. Can centrally manage images with enhanced image management capabilities, policies, and profiles. Accelerates transition from on-prem workloads to Microsoft Azure and reduces time to value
- Scales environment up or out based on schedule or load. Ramp sessions into the cloud as needed. Capacity burst, or load balance between datacenter and cloud.
- Expands compliance, security, and business requirements to the cloud.
- Enterprise-class performance, consistent user experience, advanced remote protocols deliver near-local desktop and app performance on a broad range of clients.
- Provides single flexible licensing model supporting on-premises, cloud, and hybrid environments.
- Solution to handle planned/un-planned business continuity and disaster recovery requirements.

### Qualifying questions for VMWare/Citrix control plane

- Do you have a customer which is existing client of VMWare/Citrix VDI solution, and they are happy with the product and they have required skill-set? If yes, VMWare/Citrix solution with Azure can be good option.
- Do you need to support hybrid use cases? E.g., Some users accessing desktops on-prem and some users accessing desktops in the cloud. If yes, VMWare/Citrix solution with Azure can be good option.
- Do you need scale on-prem desktops to cloud based on schedule or load/capacity burst? If yes, VMWare/Citrix solution with Azure can be good option.
- Do you need expand compliance, security, and business continuity and disaster recovery requirements to the cloud via single pane of glass? If yes, VMWare/Citrix solution with Azure can be a good option.
- Do you need to use full enterprise solution with advanced or product specific features not available in AVD? If yes, VMWare/Citrix solution with Azure can be a good option.

### Resources

- <https://azure.microsoft.com/en-us/services/virtual-desktop/citrix-virtual-apps-desktops-for-azure>
- <https://azure.microsoft.com/en-us/services/virtual-desktop/vmware-horizon-cloud>

## AVD with Nerdio or other third-party control plane

TODO

## Project Delivery Checklist

TODO
