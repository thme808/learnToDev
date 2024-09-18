# AZ104 dump
#개발/Azure

## Topic1/Question1
Your company has serval departments. Each department has a number of virtual machines (VMs).
The company has an Azure subscription that contains a resource group named RG1.
All VMs are located in RG1.
You want to associate each VM with its respective department.
What should you do?
* A. Create Azure Management Groups for each department.
* B. Create a resource group for each department.
* **C. Assign tags to the virtual machines.**
* D. Modify the settings of the virtual mac≠hines.

## Topic1/Question3
Your company has an Azure Active Directory (Azure AD) subscription.
You want to implement an Azure AD conditional access policy.
The policy must be configured to require members of the Global Administrators group to use Multi-Factor Authentication and an Azure AD-joined device when they connect to Azure AD from untrusted locations.

> Solution: **You access the Azure portal to alter the grant control of the Azure AD conditional access policy.**  

## Topic1/Question5
Your company’s Azure solution makes use of Multi-Factor Authentication for when users are not in the office. The Per Authentication option has been configured as the usage model.
After the acquisition of a smaller business and the addition of the new staff to Azure Active Directory (Azure AD) obtains a different company and adding the new employees to Azure Active Directory (Azure AD), you are informed that these employees should also make use of Multi-Factor Authentication.
To achieve this, the Per Enabled User setting must be set for the usage model.

> Solution: You **create a new Multi-Factor Authentication provider** with a backup from the existing Multi-Factor Authentication provider data.  

## Topic1/Question9
Your company has an Azure Active Directory (Azure AD) tenant named weyland.com that is configured for hybrid coexistence with the on-premises Active Directory domain.
You have a server named DirSync1 that is configured as a DirSync server.
You create a new user account in the on-premise Active Directory. You now need to replicate the user information to Azure AD immediately.

> Solution: You run the Start-ADSyncSyncCycle -PolicyType Delta PowerShell cmdlet.    
- delta, initial 둘 다 가능하지만, 신규 유저 즉시 반영이 목적이라면 delta 가 더 적합함

> The Start-ADSyncSyncCycle cmdlet has two policy types:  
> — Delta: This policy type performs a delta (or incremental) synchronization, syncing only the changes since the last sync.  
> — Initial: This policy type performs a **full synchronization**, syncing all objects and attributes.  

## Topic1/Question12
You are configuring the two datacenters as geo-clustered sites for site resiliency.
You need to recommend an Azure storage redundancy option.
You have the following data storage requirements:
	- Data must be stored on multiple nodes.
	- Data must be stored on nodes in separate geographic locations.
	- Data can be **read from the secondary location as well** as from the primary location.
Which of the following Azure stored redundancy options should you recommend?
* A. Geo-redundant storage (GRS)
	* data will be available to be read-only when failover occurs
* B. Read-only geo-redundant storage ✔️
	* RA-GRS(Read Access GRS)  is correct term, but it’s closest to the answer
* C. Zone-redundant storage
* D. Locally redundant storage

## Topic1/Question14
Your company has an azure subscription that includes a storage account, a resource group, a blob container and a file share.
A colleague named Jon Ross makes use of a solitary Azure Resource Manager (ARM) template to deploy a virtual machine and an additional Azure Storage account. You want to review the ARM template that was used by Jon Ross.

> Solution: You access the Resource Group blade.  
	- blade 는 그냥 메뉴같은 것. 
	- Resource Group 메뉴/블레이드 -> Deployments 접속해서 ARM 템플릿을 확인할 수 있음

## Topic1/Question16 #availabilitySet
Your company has three virtual machines (VMs) that are included in an **availability set**. You try to resize one of the VMs, which returns an allocation failure message. It is imperative that the VM is resized.
Which of the following actions should you take?
* A. You should only stop one of the VMs.
* B. You should stop two of the VMs.
* **C. You should stop all three VMs.**
* D. You should remove the necessary VM from the availability set.

## Topic1/Question17 
You have an Azure virtual machine (VM) that has a single data disk. You have been tasked with attaching this data disk to another Azure VM.
You need to make sure that your strategy allows for the virtual machines to be offline for the least amount of time possible.
Which of the following is the **action you should take FIRST**?

* A. Stop the VM that includes the data disk.
* B. Stop the VM that the data disk must be attached to.
* C. Detach the data disk. **Most Voted**
	*  It is possible to hot swap the disk, but it is not a best practice
* D. Delete the VM that includes the data disk.

## Topic1/Question18
You need to deploy a number of Azure virtual machines (VMs) using Azure Resource Manager (ARM) templates. You have been informed that the VMs will be included in a single availability set.
You are required to make sure that the ARM template you configure allows for as many VMs as possible to remain accessible in the event of fabric failure or maintenance.
Which of the following is the value that you should configure for the **platformFaultDomainCount** property?
* A. 10
* B. 30
* C. Min Value
* D. Max Value **Most Voted**

## Topic1/Question19
Which of the following is the value that you should configure for the **platformUpdateDomainCount** property?
* A. 10
* B. 20 **Most Voted**
* C. 30
* D. 40
> Each virtual machine in your availability set is assigned an update domain and a fault domain by the underlying Azure platform. Each availability set can be configured with up to three fault domains and twenty update domains.  

## Topic1/Question20
You have downloaded an Azure Resource Manager (ARM) template to deploy numerous virtual machines (VMs). The ARM template is based on a current VM, but must be adapted to reference an administrative password.
You need to make sure that the password cannot be stored in plain text.
You are preparing to create the necessary components to achieve your goal.
Which of the following should you create to achieve your goal? Answer by dragging the correct option from the list to the answer area.
Select and Place:
> **answers: Key vault + access policy**  
	- Azure key vault to store the password and Access policy to make it accessible. access policy is considered a legacy way to provide access to the key vault. Now you can use RBAC.

## Topic1/Question21
Your company has an Azure Active Directory (Azure AD) tenant that is configured for hybrid coexistence with the on-premises Active Directory domain.
The on-premise virtual environment consists of virtual machines (VMs) running on Windows Server 2012 R2 Hyper-V host servers.
You have created some PowerShell scripts to automate the configuration of newly created VMs. You plan to create several new VMs.
You need a solution that ensures the scripts are run on the new VMs.
Which of the following is the best solution?
* A. Configure a SetupComplete.cmd batch file in the %windir%\setup\scripts directory.**Most Voted**
	* windows 부팅시 윈도우 화면 접속 전에 스크립트 실행 됨
* B. Configure a Group Policy Object (GPO) to run the scripts as logon scripts.
* C. Configure a Group Policy Object (GPO) to run the scripts as startup scripts.
* D. Place the scripts in a new virtual hard disk (VHD).

## Topic1/Question22
Your company has an Azure Active Directory (Azure AD) tenant that is configured for hybrid coexistence with the on-premises Active Directory domain.
You plan to deploy several new virtual machines (VMs) in Azure. The VMs will have the same operating system and custom software requirements.
You configure a reference VM in the on-premise virtual environment. You then generalize the VM to create an image.
You need to upload the image to Azure to ensure that it is available for selection when you create the new Azure VMs.
Which PowerShell cmdlets should you use?
* A. Add-AzVM
* B. Add-AzVhd **Most Voted**
	* The Add-AzVhd cmdlet uploads on-premises virtual hard disks, in .vhd file format, to a blob storage account as fixed virtual hard disks.
* C. Add-AzImage
* D. Add-AzImageDataDisk

## Topic1/Question23
Your company has an Azure subscription that includes a number of Azure virtual machines (VMs), which are all part of the same virtual network.
Your company also has an on-premises Hyper-V server that hosts a VM, named VM1, which must be replicated to Azure.
Which of the following objects that must be created to achieve this goal? 
![](AZ104%20dump/FF604C05-80CA-4F62-BA72-CE6322278FD3%204.png)

## Topic1/Question24
Your company’s Azure subscription includes two Azure networks named VirtualNetworkA and VirtualNetworkB.
VirtualNetworkA includes a VPN gateway that is configured to make use of static routing. Also, a site-to-site VPN connection exists between your company’s on- premises network and VirtualNetworkA.
You have configured a point-to-site VPN connection to VirtualNetworkA from a workstation running Windows 10. After configuring virtual network peering between VirtualNetworkA and VirtualNetworkB, you confirm that you are able to access VirtualNetworkB from the company’s on-premises network. However, you find that you cannot establish a connection to VirtualNetworkB from the Windows 10 workstation.
You have to make sure that a connection to VirtualNetworkB can be established from the Windows 10 workstation.

- You choose the Allow gateway transit setting on VirtualNetworkA.
- You choose the Allow gateway transit setting on VirtualNetworkB.
- **You download and re-install the VPN client configuration package on the Windows 10 workstation.**

> 네트워크 topology가 변경되면 vpn을 재설치해야 함  
> After configuring virtual network peering between VirtualNetworkA and VirtualNetworkB, you confirm that you are able to access VirtualNetworkB from the company’s on-premises network.” This indicates the Allow/Use gateway transit is set up working. The next step will be restart/reinstall the VPN-Client config at the windows 10 workstation.  

## Topic1/Question27
Your company has virtual machines (VMs) hosted in Microsoft Azure. The VMs are located in a single Azure virtual network named VNet1.
The company has users that work remotely. The remote workers require access to the VMs on VNet1.
You need to provide access for the remote workers.
What should you do?
* A. Configure a Site-to-Site (S2S) VPN.
* B. Configure a VNet-toVNet VPN.
* C. Configure a Point-to-Site (P2S) VPN. **Most Voted**
* D. Configure DirectAccess on a Windows Server 2012 server VM.
* E. Configure a Multi-Site VPN

## Topic1/Question28
Your company has a Microsoft SQL Server Always On availability group configured on their Azure virtual machines (VMs).
You need to configure an Azure internal load balancer as a listener for the availability group.

- You create an HTTP health probe on port 1433.
- You enable Floating IP✔️
- You set Session persistence to Client IP

**Concepts explained**
 - Session persistence: a Azure term for sticky session, 클라이언트가 was1 에 처음 요청받으면 계속 was1로 받도록 유도하는 LB rule.
 - floating IP: 
	 - a Azure term for Direct Server Return.
	- LB뒤에 있는 노드(보통 db)가 클라이언트로 직접 응답하여 LB부하를 분산함. db가 여러개 구성되어 LB가 요청을 분산하는 경우 **listener를 두어 살아있는 db로 요청을 보내야 완결된 부하 분산**이라 할 수 있음. 각 vm이 고정된 내부아이피를 사용해야 listener가 각 서버의 heath check을 할 수 있음. 웹요청 시 실제 클라이언트와 직접 통신은 보안에 위배 되므로 주의.
> By enabling Floating IP, the load balancer will use a floating IP address as the source IP address for outbound flows from the backend pool. This will ensure that the **IP address used by the backend pool remains the same even if a VM is restarted or replaced**, which is important for maintaining the listener for the availability group.  

## Topic1/Question31
Your company has two on-premises servers named SRV01 and SRV02. Developers have created an application that runs on SRV01. The application calls a service on SRV02 by IP address.
You plan to migrate the application on Azure virtual machines (VMs). You have **configured two VMs on a single subnet in an Azure virtual network**. You need to configure the two VMs with **static internal IP addresses**. What should you do?
* A. Run the New-AzureRMVMConfig PowerShell cmdlet.
* B. Run the Set-AzureSubnet PowerShell cmdlet.
* C. Modify the VM properties in the Azure Management Portal.
* D. Modify the IP properties in Windows Network and Sharing Center.
* E. Run the Set-AzureStaticVNetIP PowerShell cmdlet. ✔️

## Topic1/Question32
Your company has an Azure Active Directory (Azure AD) subscription.
You need to deploy five virtual machines (VMs) to your company’s virtual network subnet.
The VMs will each have both a public and private IP address. Inbound and outbound security rules for all of these virtual machines must be identical.
Which of the following is the least amount of network interfaces needed for this configuration?
* A. 5 ✔️
* B. 10
* C. 20
* D. 40

Which of the following is the least amount of security groups needed for this configuration? 
> 1, one Network Security Group(NSR) can be assigned to multiple vm.  

## Topic1/Question34
Your company’s Azure subscription includes Azure virtual machines (VMs) that run Windows Server 2016.
One of the VMs is backed up every day using Azure Backup Instant Restore.
When the VM becomes infected with data encrypting ransomware, you decide to recover the VM’s files.
**Which of the following is TRUE in this scenario?**
* A. You can only recover the files to the infected VM.
* B. You can recover the files to any VM within the company’s subscription. ✔️
* C. You can only recover the files to a new VM.
* D. You will not be able to recover the files.

**Which of the following actions should you take?**
* A. You should restore the VM after deleting the infected VM.
* B. You should restore the VM to any VM within the company’s subscription.
* C. You should restore the VM to a new Azure VM. ✔️
* D. You should restore the VM to an on-premise Windows device.


## Topic1/Question36
You administer a solution in Azure that is currently having performance issues.
You need to find the cause of the performance issues pertaining to metrics on the Azure infrastructure.
Which of the following is the tool you should use?
* A. Azure Traffic Analytics
* B. Azure Monitor ✔️
* C. Azure Activity Log
* D. Azure Advisor

## Topic1/Question37
Your company has an Azure subscription that includes a Recovery Services vault.
You want to use Azure Backup to schedule a backup of your company's virtual machines (VMs) to the Recovery Services vault.
Which of the following VMs can you back up? Choose all that apply.
* A. VMs that run Windows 10.✔️
* B. VMs that run Windows Server 2012 or higher.✔️
* C. VMs that have NOT been shut down.✔️
* D. VMs that run Debian 8.2+.✔️
* E. VMs that have been shut down.✔️

## Topic1/Question40
You have an Azure Active Directory (Azure AD) tenant named contoso.com.
You have a CSV file that contains the names and email addresses of 500 external users.
You need to create a guest user account in contoso.com for each of the 500 external users.
**Solution: You create a PowerShell script that runs the New-AzureADMSInvitation cmdlet for each external user.**

## Topic2/Question1
You have an Azure subscription named Subscription1 that contains a resource group named RG1.
In RG1, you create an internal load balancer named LB1 and a public load balancer named LB2.
You need to ensure that an administrator named Admin1 can manage LB1 and LB2. The solution must follow **the principle of least privilege**.
Which role should you assign to Admin1 for each task? To answer, select the appropriate options in the answer area.
![](AZ104%20dump/932E9687-C584-465F-975B-7C0AF92038FE%204.png)
-  LB와 backend pool(vm)에 모두에 접근 가능해야함 -> network contributor 역할이**RG level에 할당되어야** 함.
- health probe도 RG레벨에서 접근가능 함

> Network Contributor lets you manage networks, but not access to them.  
> Users assigned the Network contributor role can configure and manage network-related resources but do not have access to other Azure resources outside the networking scope.  

## Topic2/Question2
You have an Azure subscription that contains an Azure Active Directory (Azure AD) tenant named contoso.com and an Azure Kubernetes Service (AKS) cluster named AKS1.
An administrator reports that she is unable to grant access to AKS1 to the users in contoso.com.
You need to ensure that access to AKS1 can be granted to the contoso.com users.
What should you do first?
* A. From contoso.com, modify the Organization relationships settings.
* B. From contoso.com, create an OAuth 2.0 authorization endpoint. ✔️
	* 쿠버네티스 접근을 위한 토큰이 생성되어야 함
	* AKS now supports direct integration with Azure AD, the method using OAuth 2.0 is considered legacy
* C. Recreate AKS1.
* D. From AKS1, create a namespace.

## Topic2/Question3
You have a Microsoft 365 tenant and an Azure Active Directory (Azure AD) tenant named contoso.com.
You plan to grant three users named User1, User2, and User3 access to a temporary Microsoft SharePoint document library named Library1.
You need to create groups for the users. The solution must ensure that the groups are deleted automatically after 180 days.
Which two groups should you create?
* A. a Microsoft 365 group that uses the Assigned membership type✔️
* B. a Security group that uses the Assigned membership type
* C. a Microsoft 365 group that uses the Dynamic User membership type✔️
* D. a Security group that uses the Dynamic User membership type
* E. a Security group that uses the Dynamic Device membership type

## Topic2/Question4
You have an Azure Active Directory (Azure AD) tenant named contoso.com that contains the users shown in the following table:
![](AZ104%20dump/2308337E-C9E6-4B32-BD5C-3E793D1127B2%204.png)
— User3 is the owner of Group1. Group2 is a member of Group1.
You configure an access review named Review1 as shown in the following exhibit:
![](AZ104%20dump/0F12E6E8-16D7-425C-A8CE-48EDB46105FC%204.png)

- note that scope is **Guest users only**
- Reviewers are **Group Owners**
![](AZ104%20dump/D85F0920-784C-4CD3-BC73-9838CE863B03%204.png)
- NNN

## Topic2/Question5
You have the Azure management groups shown in the following table:
![](AZ104%20dump/55047A69-41C7-425A-9B03-F246EF630DFD%204.png)
You add Azure subscriptions to the management groups as shown in the following table:
![](AZ104%20dump/F70CC2E5-9178-45DE-8F7C-62709DE0205C%204.png)
You create the Azure policies shown in the following table:
![](AZ104%20dump/DFE52F83-147F-4D4A-8F36-8D4706FFECFE%204.png)

![](AZ104%20dump/37214963-CFB4-41CD-9CA4-1B97A6439BA5%204.png)
- NNN

## Topic2/Question6
![](AZ104%20dump/F5450418-1B5B-4532-98F4-4ACF92F13D2E%204.png)
What is the effect of the policy?
* A. You are prevented from creating Azure SQL servers anywhere in Subscription 1.
* B. You can create Azure SQL servers in ContosoRG1 only.
* C. You are prevented from creating Azure SQL Servers in ContosoRG1 only.
* D. You can create Azure SQL servers in any resource group within Subscription 1.

## Topic2/Question7
![](AZ104%20dump/6D2ED933-CF06-4766-A5CB-AE748A2E36FA%204.png)
- Apply tag and its default value -> Append a tag and its value to resources
- Policy 적용 후에는 tag를 지정하더라도 default tag가 붙음 (아래 VNET3)
- Policy 적용 전 생성된 VNET1은 remediation 해야 default tag 붙음
![](AZ104%20dump/488C37F4-0892-4C86-95E2-DBCFF1C2C7FD%204.png)

## Topic2/Question8
You have an Azure subscription named AZPT1 that contains the resources shown in the following table:
![](AZ104%20dump/0004900001%204.png)

You create a new Azure subscription named AZPT2.
You need to identify which resources can be moved to AZPT2.
Which resources should you identify? **ALL**


## Topic2/Question9
You recently created a new Azure subscription that contains a user named Admin1.
Admin1 attempts to deploy an Azure Marketplace resource by using an Azure Resource Manager template. Admin1 deploys the template by using Azure
PowerShell and receives the following error message: `User failed validation to purchase resources. Legal terms have not been accepted for this item on this subscription. To accept legal terms, please go to the Azure portal (http://go.microsoft.com/fwlink/?LinkId=534873) and configure programmatic deployment for the Marketplace item or create it there for the first time.`
You need to ensure that Admin1 can deploy the Marketplace resource successfully.
What should you do?
* A. From Azure PowerShell, run the Set-AzApiManagementSubscription cmdlet
* B. From the Azure portal, register the Microsoft.Marketplace resource provider
* C. From Azure PowerShell, run the Set-AzMarketplaceTerms cmdlet✔️
* D. From the Azure portal, assign the Billing administrator role to Admin1

## Topic2/Question10
You have an Azure Active Directory (Azure AD) tenant that contains 5,000 user accounts.
You create a new user account named AdminUser1.
You need to assign the User administrator administrative role to AdminUser1.
What should you do from the user account properties?
* A. From the Licenses blade, assign a new license
* B. From the Directory role blade, modify the directory role ✔️
* C. From the Groups blade, invite the user account to a new group

## Topic2/Question11
You have an Azure Active Directory (Azure AD) tenant named contoso.onmicrosoft.com that contains 100 user accounts.
You purchase 10 Azure AD Premium P2 licenses for the tenant.
You need to ensure that 10 users can use all the Azure AD Premium features.
What should you do?
* A. From the Licenses blade of Azure AD, assign a license ✔️
* B. From the Groups blade of each user, invite the users to a group
* C. From the Azure AD domain, add an enterprise application
* D. From the Directory role blade of each user, modify the directory role

## Topic2/Question12
You have an Azure subscription named Subscription1 and an on-premises deployment of Microsoft System Center Service Manager.
Subscription1 contains a virtual machine named VM1.
You need to ensure that an alert is set in Service Manager when the amount of available memory on VM1 is below 10 percent.
What should you do first?
* A. Create an automation runbook
* B. Deploy a function app
* C. Deploy the IT Service Management Connector (ITSM)  ✔️
* D. Create a notification

## Topic2/Question13
You sign up for Azure Active Directory (Azure AD) Premium P2.
You need to **add a user named admin1@contoso.com as an administrator on all the computers** that will be joined to the Azure AD domain.
What should you configure in Azure AD?
* A. Device settings from the Devices blade  ✔️
* B. Providers from the MFA Server blade
* C. User settings from the Users blade
* D. General settings from the Groups blade

## Topic2/Question14
You have Azure Active Directory tenant named Contoso.com that includes following users:
![](AZ104%20dump/C3C235A1-CB81-480A-AF21-7DDFCC96DE37%202.png)

Contoso.com includes following Windows 10 devices:
![](AZ104%20dump/96CF65F9-EBB3-4259-AF0E-6EF06BC0EB4D%202.png)

You create following security groups in Contoso.com:
![](AZ104%20dump/9A03B30A-E6B9-4F07-8B70-852ECF5D9422%202.png)

![](AZ104%20dump/EB998EAA-3251-4030-931B-05AE86C2ABF9%202.png)
- NYN

> As a global administrator or cloud device administrator, you can manage the registered or joined devices. User administrator can manage users but not devices.  
>   
> User1 is a cloud device administrator. Although the role can manage the registered or joined devices, it does not grant permissions to manage any other properties on the device. Users in this role cannot change the group membership for Group1.   
>   
> User2 is the group owner of Group1, which has the requisite authority for changing group membership. He can add Device1 to Group1 regardless of his role.  
>   
> Group2 has Dynamic Device membership type, which do not require manual intervention. simply put, you can’t manually add or remove a member of a dynamic group.  

## Topic2/Question15
You have an Azure subscription that contains a resource group named RG26.
RG26 is set to the West Europe location and is used to create temporary resources for a project. RG26 contains the resources shown in the following table.
![](AZ104%20dump/F1244E34-05CD-4575-9F73-F081F6C7F003%202.png)
SQLDB01 is backed up to RGV1.
When the project is complete, you attempt to delete RG26 from the Azure portal. The deletion fails.
You need to delete RG26.
What should you do first?
* A. Delete VM1
* B. Stop VM1
* C. Stop the backup of SQLDB01 ✔️
* D. Delete sa001 

![](AZ104%20dump/D9875E7F-3AF1-4F6D-A4A3-35FDAE16E603%202.png)

## Topic2/Question16
You have an Azure subscription named Subscription1 that contains a virtual network named VNet1. VNet1 is in a resource group named RG1.
Subscription1 has a user named User1. User1 has the following roles:
	- ✑ Reader
	- ✑ Security Admin
	- ✑ Security Reader
You need to ensure that User1 can **assign the Reader role for VNet1 to other users.**
What should you do?
* A.Remove User1 from the Security Reader and Reader roles for Subscription1.
* B. Assign User1 the User Access Administrator role for VNet1. ✔️
	* or  Assign User1 the Owner role for VNet1.
* C. Assign User1 the Network Contributor role for VNet1.
* D. Assign User1 the Network Contributor role for RG1.

> **Network Contributor** lets you manage networks, but not access to them. Users assigned the Network contributor role can configure and manage network-related resources but do not have access to other Azure resources outside the networking scope.  

> **User Access Administrator** lets you manage user access to Azure resources. By default, only users with the `Owner` or `User Access Administrator` roles can assign roles  to others.  
![](AZ104%20dump/9EB1DFE4-B3B7-4482-BB4B-74036F5B9521%202.png)

## Topic2/Question17
You have an Azure Active Directory (Azure AD) tenant named contosocloud.onmicrosoft.com.
Your company has a **public DNS zone** for contoso.com.
You add contoso.com as a custom domain name to Azure AD.
You need to ensure that Azure can verify the domain name.
Which type of DNS record should you create?
* A. MX ✔️
* B. NSEC
* C. PTR
* D. RRSIG

> menu: Azure portal > Microsoft Entra ID > Custom domain names  
> you can see that **TXT and MX are available options for DNS record type**.  
![](AZ104%20dump/BCD4F844-1F4C-4B60-BC10-8F6074014D49%202.png)

## Topic2/Question18
You have an Azure Directory (Azure AD) tenant named Adatum and an Azure Subscription named Subscription1. Adatum contains a group named Developers.
Subscription1 contains a resource group named Dev.
You need to provide the Developers group with the ability to create Azure logic apps in the Dev resource group.

- On Subscription1, you assign the DevTest Labs User role to the Developers 
- On Subscription1, you assign the Logic App Operator role to the Developers group.
- On Dev, you assign the Contributor role to the Developers group  ✔️

> DevTest Labs User role only lets you connect, start, restart, and shutdown virtual machines in your Azure DevTest Labs. The Logic App Contributor role lets you manage logic app, but not access to them. It provides access to view, edit, and update a logic app.  

## Topic2/Question21
You have an Azure subscription that is used by four departments in your company. The subscription contains 10 resource groups. **Each department uses resources in several resource groups**.
You need to send a report to the finance department. **The report must detail the costs for each department.**
Which three actions should you perform in sequence? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order.
Select and Place:
![](AZ104%20dump/F374E9C4-8A01-4691-AE37-195CC7CAFD46.png)

## Topic2/Question22
You have an Azure subscription named Subscription1 that contains an Azure Log Analytics workspace named Workspace1.
You need to view the error events from a table named Event.
Which query should you run in Workspace1?
* A. Get-Event Event | where {$_.EventType == “error”}
* B. search in (Event) “error” ✔️
* C. select * from Event where EventType == “error”
* D. search in (Event) * | where EventType -eq “error”

> Kusto Query Language (KQL) is Log Analytics query language.  
> options D seems to have similar syntax to KQL, but can be corrected to  `search in (Event) * | where EventType == "error"`  

## Topic2/Question23
You have an Azure subscription that contains a virtual network named VNET1 in the East US 2 region. A network interface named VM1-NI is connected to VNET1.
You **successfully deployed** the following Azure Resource Manager template.
![](AZ104%20dump/133026EC-CB2C-4D64-BBAE-8A4FAE963F36.png)

![](AZ104%20dump/918353B4-5544-499D-9808-8B6D2143AF10.png)

## Topic2/Question24
You have an Azure subscription named Subscription1. Subscription1 contains the resource groups in the following table.
![](AZ104%20dump/92A2D270-3117-49FA-AC07-6F4265CD4673.png)

RG1 has a web app named WebApp1. WebApp1 is located in West Europe.
You move WebApp1 to RG2.
What is the effect of the move?
* A. The App Service plan for WebApp1 remains in West Europe. Policy2 applies to WebApp1. ✔️
* B. The App Service plan for WebApp1 moves to North Europe. Policy2 applies to WebApp1.
* C. The App Service plan for WebApp1 remains in West Europe. Policy1 applies to WebApp1.
* D. The App Service plan for WebApp1 moves to North Europe. Policy1 applies to WebApp1.

## Topic2/Question25
You have an Azure subscription named Subscription1 that has a subscription ID of c276fc76-9cd4-44c9-99a7-4fd71546436e.
You need to **create a custom RBAC role named CR1** that meets the following requirements:
- ✑ Can be assigned only to the resource groups in Subscription1
- ✑ Prevents the management of the access permissions for the resource groups
- ✑ Allows the viewing, creating, modifying, and deleting of resources within the resource groups
What should you specify in the assignable scopes and the permission elements of the definition of CR1? To answer, select the appropriate options in the answer area.
[음악](file:///Users/thme808/Downloads/음악) ![](AZ104%20dump/3A0B61AD-708B-49DB-A9C4-CD3CD04878B9.png)
- answers: second one, first one

> you cannot wildcard all of them using /resourceGroups. RG name need be specified and even then applies to one particular RG  

## Topic2/Question26
Users access the resources in the subscription from either home or from customer sites. From home, users must establish a **point-to-site VPN** to access the Azure resources. The users on the customer sites access the Azure resources by using **site-to-site VPNs**.
You have a line-of-business-app named App1 that runs on several Azure virtual machine. The virtual machines run Windows Server 2016.
You need to ensure that the connections to App1 are spread across all the virtual machines.
What are **two possible Azure services** that you can use? Each correct answer presents a complete solution.
* A. an internal load balancer ✔️
* B. a public load balancer
* C. an Azure Content Delivery Network (CDN)
* D. Traffic Manager
* E. an Azure Application Gateway ✔️

> A: The customer sites are connected through VPNs, so an internal load balancer is enough.   
>   
> B: The customer sites are connected through VPNs, so there’s no need for a public load balancer, an internal load balancer is enough.  
>   
> C: A CDN does not provide load balancing for applications, so it not relevant for this situation.  
>   
> D: Traffic manager is a DNS based solution to direct users’ requests to the nearest (typically) instance and does not provide load balancing for this situation.  
>   
> E: Azure Application Gateway is a valid option, as it provides load balancing in addition to routing and security functions  

## Topic2/Question27
You have 100 Azure virtual machines.
You need to quickly identify underutilized virtual machines that can have their service tier changed to a less expensive offering.
Which blade should you use?
* A. Monitor
* B. Advisor ✔️
* C. Metrics
* D. Customer insights

> Advisor helps you optimize and reduce your overall Azure spend by identifying idle and underutilized resources. You can get cost recommendations from the Cost tab on the Advisor dashboard.  

## Topic2/Question28
You have an Azure Active Directory (Azure AD) tenant.
You need to create a conditional access policy that requires all users to use multi-factor authentication when they access the Azure portal.
Which **three** settings should you configure? To answer, select the appropriate settings in the answer area.
![](AZ104%20dump/D4ED7406-A7FC-46C1-8C0F-69F05A5833A7.png)


> — Select Users & Groups : Where you have to choose all users.  
> — Select Cloud apps or actions: to specify the Azure portal  
> — Grant: to grant the MFA.  

## Topic2/Question29
You have an Azure Active Directory (Azure AD) tenant named contoso.onmicrosoft.com. The User administrator role is assigned to a user named Admin1. An external partner has a Microsoft account that uses the user1@outlook.com sign in.
Admin1 attempts to invite the external partner to sign in to the Azure AD tenant and receives the following error message: `Unable to invite user user1@outlook.com. Generic authorization exception.`
You need to ensure that Admin1 can invite the external partner to sign in to the Azure AD tenant.
What should you do?
* A. From the Users settings blade, modify the External collaboration settings. ✔️
* B. From the Custom domain names blade, add a custom domain.
* C. From the Organizational relationships blade, add an identity provider.
* D. From the Roles and administrators blade, assign the Security administrator role to Admin1.

## Topic2/Question30 
You have an Azure subscription linked to an Azure Active Directory tenant. The tenant includes a user account named User1.
You need to ensure that User1 can assign a policy to the tenant root management group. What should you do?
* A. Assign the Owner role for the Azure Subscription to User1, and then modify the default conditional access policies.
* B. Assign the Owner role for the Azure subscription to User1, and then instruct User1 to configure access management for Azure resources.
* C. Assign the Global administrator role to User1, and then instruct User1 to configure access management for Azure resources. ✔️
* D. Create a new management group and delegate User1 as the owner of the new management group.
> B or C???  

![](AZ104%20dump/468DC18D-D929-43C4-9C47-B5E6232C166D.png)