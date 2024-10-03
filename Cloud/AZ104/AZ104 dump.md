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
* C. Assign tags to the virtual machines. ✔️
* D. Modify the settings of the virtual machine.

## Topic1/Question3
Your company has an Azure Active Directory (Azure AD) subscription.
You want to implement an Azure AD conditional access policy.
The policy must be configured to require members of the Global Administrators group to use Multi-Factor Authentication and an Azure AD-joined device when they connect to Azure AD from untrusted locations.

- Solution: You access the Azure portal to alter the **grant control** of the Azure AD conditional access policy.

## Topic1/Question5
Your company’s Azure solution makes use of Multi-Factor Authentication for when users are not in the office. The Per Authentication option has been configured as the usage model.
After the acquisition of a smaller business and the addition of the new staff to Azure Active Directory (Azure AD) obtains a different company and adding the new employees to Azure Active Directory (Azure AD), you are informed that these employees should also make use of Multi-Factor Authentication.
To achieve this, the Per Enabled User setting must be set for the usage model.

- Solution: You **create a new Multi-Factor Authentication provider** with a backup from the existing Multi-Factor Authentication provider data.

## Topic1/Question9
Your company has an Azure Active Directory (Azure AD) tenant named weyland.com that is configured for hybrid coexistence with the on-premises Active Directory domain.
You have a server named DirSync1 that is configured as a DirSync server.
You create a new user account in the on-premise Active Directory. You now need to replicate the user information to Azure AD immediately.

- Solution: You run the **Start-ADSyncSyncCycle -PolicyType Delta** PowerShell cmdlet.  

> delta, initial 둘 다 가능하지만, 신규 유저 즉시 반영이 목적이라면 delta 가 더 적합함  
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

- Solution: You access the Resource Group blade.

> blade 는 그냥 메뉴같은 것.   
> Resource Group 메뉴/블레이드 -> Deployments 접속해서 ARM 템플릿을 확인할 수 있음  

## Topic1/Question16/Availability Set
Your company has three virtual machines (VMs) that are included in an **availability set**. You try to resize one of the VMs, which returns an allocation failure message. It is imperative that the VM is resized.
Which of the following actions should you take?
* A. You should only stop one of the VMs.
* B. You should stop two of the VMs.
* C. You should stop all three VMs. ✔️
* D. You should remove the necessary VM from the availability set.

## Topic1/Question18/Availability Set
You need to deploy a number of Azure virtual machines (VMs) using Azure Resource Manager (ARM) templates. You have been informed that the VMs will be included in a single availability set.
You are required to make sure that the ARM template you configure allows for as many VMs as possible to remain accessible in the event of fabric failure or maintenance.
Which of the following is the value that you should configure for the **platformFaultDomainCount** property?
* A. 10
* B. 30
* C. Min Value
* D. Max Value ✔️

## Topic1/Question19/Availability Set
Which of the following is the value that you should configure for the **platformUpdateDomainCount** property?
* A. 10
* B. 20 ✔️
* C. 30
* D. 40

> Each virtual machine in your availability set is assigned an update domain and a fault domain by the underlying Azure platform. Each availability set can be configured with **up to three fault domains and twenty update domains**.  

## Topic4/Question13/Availability Set
You have an app named App1 that runs on two Azure virtual machines named VM1 and VM2.
You plan to implement an Azure Availability Set for App1. The solution must ensure that App1 is available during planned maintenance of the hardware hosting VM1 and VM2.
What should you include in the Availability Set?
* A. one update domain
* B. two fault domains
* C. one fault domain
* D. two update domains ✔️

> - planned maintenance > update domain  
> - unplanned maintenance  >  fault domain  
>    
> planned maintenance 동안 vm1과 vm2가 동시에 downtime을 가지지 않으려면 최소 2개의 update domain이 필요함.  

## Topic4/Question13/Availability Set
You plan to move a distributed on-premises app named App1 to an Azure subscription.
After the planned move, App1 will be hosted on several Azure virtual machines.
You need to ensure that App1 always runs on at least eight virtual machines during planned Azure maintenance.
What should you create?
* A. one virtual machine scale set that has 10 virtual machines instances
* B. one Availability Set that has three fault domains and one update domain
* C. one Availability Set that has 10 update domains and one fault domain
* D. one virtual machine scale set that has 12 virtual machines instances

## Topic1/Question17 
You have an Azure virtual machine (VM) that has a single data disk. You have been tasked with attaching this data disk to another Azure VM.
You need to make sure that your strategy allows for the virtual machines to be offline for the least amount of time possible.
Which of the following is the **action you should take FIRST**?
* A. Stop the VM that includes the data disk.
* B. Stop the VM that the data disk must be attached to.
* C. Detach the data disk. ✔️
* D. Delete the VM that includes the data disk.

## Topic1/Question20
You have downloaded an Azure Resource Manager (ARM) template to deploy numerous virtual machines (VMs). The ARM template is based on a current VM, but must be adapted to reference an administrative password.
You need to make sure that the password cannot be stored in plain text.
You are preparing to create the necessary components to achieve your goal.
Which of the following should you create to achieve your goal? Answer by dragging the correct option from the list to the answer area.
Select and Place:
- **answers: Key vault + access policy**

> Azure key vault to store the password and Access policy to make it accessible. access policy is considered a legacy way to provide access to the key vault. Now you can use RBAC.  

## Topic1/Question21
Your company has an Azure Active Directory (Azure AD) tenant that is configured for hybrid coexistence with the on-premises Active Directory domain.
The on-premise virtual environment consists of virtual machines (VMs) running on Windows Server 2012 R2 Hyper-V host servers.
You have created some PowerShell scripts to automate the configuration of newly created VMs. You plan to create several new VMs.
You need a solution that ensures the scripts are run on the new VMs.
Which of the following is the best solution?

* A. Configure a SetupComplete.cmd batch file in the %windir%\setup\scripts directory. ✔️	(* windows 부팅시 윈도우 화면 접속 전에 스크립트 실행 됨)
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
* B. Add-AzVhd ✔️	
* C. Add-AzImage
* D. Add-AzImageDataDisk

> The Add-AzVhd cmdlet uploads on-premises virtual hard disks, in .vhd file format, to a blob storage account as fixed virtual hard disks.  

## Topic1/Question23
Your company has an Azure subscription that includes a number of Azure virtual machines (VMs), which are all part of the same virtual network.
Your company also has an on-premises Hyper-V server that hosts a VM, named VM1, which must be replicated to Azure.
Which of the following objects that must be created to achieve this goal? 
![](AZ104%20dump/FF604C05-80CA-4F62-BA72-CE6322278FD3%2022.png)

## Topic1/Question24
Your company’s Azure subscription includes two Azure networks named VirtualNetworkA and VirtualNetworkB.
VirtualNetworkA includes a VPN gateway that is configured to make use of static routing. Also, a site-to-site VPN connection exists between your company’s on- premises network and VirtualNetworkA.
You have configured a point-to-site VPN connection to VirtualNetworkA from a workstation running Windows 10. After configuring virtual network peering between VirtualNetworkA and VirtualNetworkB, you confirm that you are able to access VirtualNetworkB from the company’s on-premises network. However, you find that you cannot establish a connection to VirtualNetworkB from the Windows 10 workstation.
You have to make sure that a connection to VirtualNetworkB can be established from the Windows 10 workstation.
- You choose the Allow gateway transit setting on VirtualNetworkA.
- You choose the Allow gateway transit setting on VirtualNetworkB.
- You download and re-install the VPN client configuration package on the Windows 10 workstation. ✔️

> 네트워크 topology가 변경되면 vpn을 재설치해야 함  
> After configuring virtual network peering between VirtualNetworkA and VirtualNetworkB, you confirm that you are able to access VirtualNetworkB from the company’s on-premises network.” This indicates the Allow/Use gateway transit is set up working. The next step will be restart/reinstall the VPN-Client config at the windows 10 workstation.  

## Topic1/Question27
Your company has virtual machines (VMs) hosted in Microsoft Azure. The VMs are located in a single Azure virtual network named VNet1.
The company has users that work remotely. The remote workers require access to the VMs on VNet1.
You need to provide access for the remote workers.
What should you do?
* A. Configure a Site-to-Site (S2S) VPN.
* B. Configure a VNet-toVNet VPN.
* C. Configure a Point-to-Site (P2S) VPN. ✔️
* D. Configure DirectAccess on a Windows Server 2012 server VM.
* E. Configure a Multi-Site VPN

## Topic1/Question28
Your company has a Microsoft SQL Server Always On availability group configured on their Azure virtual machines (VMs).
You need to configure an Azure internal load balancer as a listener for the availability group.
- You create an HTTP health probe on port 1433.
- You enable Floating IP ✔️
- You set Session persistence to Client IP

> — **Session persistence**: a Azure term for sticky session, 클라이언트가 was1 에 처음 요청받으면 계속 was1로 받도록 유도하는 LB rule.  
> — **floating IP**:  a Azure term for Direct Server Return. LB뒤에 있는 노드(보통 db)가 클라이언트로 직접 응답하여 LB부하를 분산함. db가 여러개 구성되어 LB가 요청을 분산하는 경우 **listener를 두어 살아있는 db로 요청을 보내야 완결된 부하 분산**이라 할 수 있음. 각 vm이 고정된 내부아이피를 사용해야 listener가 각 서버의 heath check을 할 수 있음. 웹요청 시 실제 클라이언트와 직접 통신은 보안에 위배 되므로 주의.  
>   
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
- 1, one Network Security Group(NSR) can be assigned to multiple vm.

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
You need to create a **guest user account** in contoso.com for each of the 500 external users.

- You create a PowerShell script that runs the **New-AzureADMSInvitation** cmdlet for each external user. ✔️
- You create a PowerShell script that runs the New-MgUser cmdlet for each external user.
- You create a PowerShell script that runs the **New-MgInvitation** cmdlet for each external user. ✔️

## Topic2/Question1
You have an Azure subscription named Subscription1 that contains a resource group named RG1.
In RG1, you create an internal load balancer named LB1 and a public load balancer named LB2.
You need to ensure that an administrator named Admin1 can manage LB1 and LB2. The solution must follow **the principle of least privilege**.
Which role should you assign to Admin1 for each task? To answer, select the appropriate options in the answer area.
![](AZ104%20dump/932E9687-C584-465F-975B-7C0AF92038FE%2022.png)
- third one, third one

> LB와 backend pool(vm)에 모두에 접근 가능해야함 -> network contributor 역할이**RG level에 할당되어야** 함.   
> health probe도 RG레벨에서 접근가능 함  

> Network Contributor lets you manage networks, but not access to them.  
> Users assigned the Network contributor role can configure and manage network-related resources but do not have access to other Azure resources outside the networking scope.  

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

> **Owner** grants full access to manage all resources, including the ability to assign roles in Azure RBAC.  

![](AZ104%20dump/9EB1DFE4-B3B7-4482-BB4B-74036F5B9521%2020.png)


## Topic2/Question52
You have an Azure Load Balancer named LB1.
You assign a user named User1 the roles shown in the following exhibit.
![](AZ104%20dump/0010800001%2016.jpg)
Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.

![](AZ104%20dump/0010900002%2016.jpg)

## Topic2/Question56
You have 15 Azure subscriptions.
You have an Azure Active Directory (Azure AD) tenant that contains a security group named Group1.
You plan to purchase additional Azure subscription.
You need to ensure that **Group1 can manage role assignments for the existing subscriptions and the planned subscriptions**. The solution must meet the following requirements:
- ✑ Use the principle of least privilege.
- ✑ Minimize administrative effort.

What should you do?
* A. Assign Group1 the Owner role for the root management group.
* B. Assign Group1 the User Access Administrator role for the root management group. ✔️
* C. Create a new management group and assign Group1 the User Access Administrator role for the group.
* D. Create a new management group and assign Group1 the Owner role for the group.

## Topic2/Question62
You have an Azure Subscription that contains a storage account named storageacct1234 and two users named User1 and User2.
You assign User1 the roles shown in the following exhibit.

![](AZ104%20dump/0012500001%207.jpg)

Which two actions can User1 perform? Each correct answer presents a complete solution.
* A. Assign roles to User2 for storageacct1234.
* B. Upload blob data to storageacct1234. ✔️
* C. Modify the firewall of storageacct1234.
* D. View blob data in storageacct1234. ✔️
* E. View file shares in storageacct1234. 
	* storage account contributor role

![](AZ104%20dump/F8B3800C-17C7-47BE-A553-4ED501A82179%205.png)

## Topic2/Question2
You have an Azure subscription that contains an Azure Active Directory (Azure AD) tenant named contoso.com and an Azure Kubernetes Service (AKS) cluster named AKS1.
An administrator reports that she is unable to grant access to AKS1 to the users in contoso.com.
You need to ensure that access to AKS1 can be granted to the contoso.com users.
What should you do first?
* A. From contoso.com, modify the Organization relationships settings.
* B. From contoso.com, create an OAuth 2.0 authorization endpoint. ✔️
* C. Recreate AKS1.
* D. From AKS1, create a namespace.

> 쿠버네티스 접근을 위한 토큰이 생성되어야 함  
> AKS now supports direct integration with Azure AD, the method using OAuth 2.0 is considered legacy  

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
![](AZ104%20dump/2308337E-C9E6-4B32-BD5C-3E793D1127B2%2022.png)

User3 is the owner of Group1. Group2 is a member of Group1.
You configure an access review named Review1 as shown in the following exhibit:
![](AZ104%20dump/0F12E6E8-16D7-425C-A8CE-48EDB46105FC%2022.png)

![](AZ104%20dump/D85F0920-784C-4CD3-BC73-9838CE863B03%2022.png)
- NNN

> note that scope is **Guest users only**. Reviewers are **Group Owners**  

## Topic2/Question5
You have the Azure management groups shown in the following table:
![](AZ104%20dump/55047A69-41C7-425A-9B03-F246EF630DFD%2022.png)
You add Azure subscriptions to the management groups as shown in the following table:
![](AZ104%20dump/F70CC2E5-9178-45DE-8F7C-62709DE0205C%2022.png)
You create the Azure policies shown in the following table:
![](AZ104%20dump/DFE52F83-147F-4D4A-8F36-8D4706FFECFE%2022.png)

![](AZ104%20dump/37214963-CFB4-41CD-9CA4-1B97A6439BA5%2022.png)
- NNN

## Topic2/Question6
![](AZ104%20dump/F5450418-1B5B-4532-98F4-4ACF92F13D2E%2022.png)
What is the effect of the policy?
* A. You are prevented from creating Azure SQL servers anywhere in Subscription 1.
* B. You can create Azure SQL servers in ContosoRG1 only.
* C. You are prevented from creating Azure SQL Servers in ContosoRG1 only.
* D. You can create Azure SQL servers in any resource group within Subscription 1.

## Topic2/Question7
![](AZ104%20dump/6D2ED933-CF06-4766-A5CB-AE748A2E36FA%2022.png)
> 정정: Apply tag and its default value -> **Append a tag and its value to resources**  

- VNET1 - `Department: D1`
	- Policy 적용 전 생성된 resource는 remediation task를 수행해야 policy의 default tag 붙음. 그 전에는 변화 없음.
- VNET2 -  `Label: Value1`
	- Policy 적용 후에는 tag에 policy의 default tag가 이어서 붙음 (아래 VNET3 이미지 참조)
- RG6 - `RGroup: RG6`
	- Resource Group, Subscription 은 Resource 가 아니므로 policy 정책에서 예외임.

![](AZ104%20dump/488C37F4-0892-4C86-95E2-DBCFF1C2C7FD%2022.png)

## Topic2/Question48
You have an Azure subscription named Sub1 that contains the Azure resources shown in the following table.

![](AZ104%20dump/0010400001%2017.png)

You assign an Azure policy that has the following settings:
- ✑ Scope: Sub1
- ✑ Exclusions: Sub1/RG1/VNET1
- ✑ Policy definition: Append a tag and its value to resources
- ✑ Policy enforcement: Enabled
- ✑ Tag name: Tag4
- ✑ Tag value: value4

You assign tags to the resources as shown in the following table.

![](AZ104%20dump/0010400008%2017.png)

For each of the following statements, select Yes if the statement is true. Otherwise, select No.

![](AZ104%20dump/F69A1104-1DA3-41BE-871E-2A0F73340BC0%2010.png)

> Box 1: Yes -  
> **“Append a tag and its value to resources” : this policy does not apply to Resource Groups**.   
>   
> Box 2: No -  
> Tags applied to the resource group or subscription aren’t inherited by the resources although you can enable inheritance with Azure Policy. Storage1 has Tag3:Value1 and the Azure Policy will add Tag4.   
>   
> Box 3: No -  
> Tags applied to the resource group or subscription aren’t inherited by the resources so VNET1 does not have Tag2.  
> VNET1 has Tag3:value2. VNET1 is excluded from the Azure Policy so Tag4 will not be added to VNET1.  

## Topic2/Question8
You have an Azure subscription named AZPT1 that contains the resources shown in the following table:

![](AZ104%20dump/0004900001%2022.png)

You create a new Azure subscription named AZPT2.
You need to identify which resources can be moved to AZPT2.
Which resources should you identify? 
- **ALL**


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

![](AZ104%20dump/C3C235A1-CB81-480A-AF21-7DDFCC96DE37%2020.png)

Contoso.com includes following Windows 10 devices:
![](AZ104%20dump/96CF65F9-EBB3-4259-AF0E-6EF06BC0EB4D%2020.png)

You create following security groups in Contoso.com:
![](AZ104%20dump/9A03B30A-E6B9-4F07-8B70-852ECF5D9422%2020.png)

![](AZ104%20dump/EB998EAA-3251-4030-931B-05AE86C2ABF9%2020.png)
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

![](AZ104%20dump/F1244E34-05CD-4575-9F73-F081F6C7F003%2020.png)

SQLDB01 is backed up to RGV1.
When the project is complete, you attempt to delete RG26 from the Azure portal. The deletion fails.
You need to delete RG26.
What should you do first?
* A. Delete VM1
* B. Stop VM1
* C. Stop the backup of SQLDB01 ✔️
* D. Delete sa001 

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

![](AZ104%20dump/BCD4F844-1F4C-4B60-BC10-8F6074014D49%2020.png)

## Topic2/Question18
You have an Azure Directory (Azure AD) tenant named Adatum and an Azure Subscription named Subscription1. Adatum contains a group named Developers.
Subscription1 contains a resource group named Dev.
You need to provide the Developers group with the ability to create Azure logic apps in the Dev resource group.

- On Subscription1, you assign the DevTest Labs User role to the Developers 
- On Subscription1, you assign the Logic App Operator role to the Developers group.
- On Dev, you assign the Contributor role to the Developers group  ✔️

> DevTest Labs User role only lets you connect, start, restart, and shutdown virtual machines in your Azure DevTest Labs. The Logic App Contributor role lets you manage logic app, but not access to them. It provides access to view, edit, and update a logic app.  

## Topic2/Question51
You need to provide the Developers group with the ability to create Azure logic apps in the Dev resource group.
> Solution: On Dev, you assign the Logic App Contributor role to the Developers group.  

Does this meet the goal?
* A. Yes ✔️
* B. No

## Topic2/Question21
You have an Azure subscription that is used by four departments in your company. The subscription contains 10 resource groups. **Each department uses resources in several resource groups**.
You need to send a report to the finance department. **The report must detail the costs for each department.**
Which three actions should you perform in sequence? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order.
Select and Place:

![](AZ104%20dump/F374E9C4-8A01-4691-AE37-195CC7CAFD46%2019.png)

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

## Topic2/Question63
You have an Azure subscription named Subscription1 that contains an Azure Log Analytics workspace named Workspace1.
You need to view the error events from a table named Event.
Which query should you run in Workspace1?
* A. select * from Event where EventType == “error”
* B. Event | search “error” ✔️
* C. Event | where EventType is “error”
* D. Get-Event Event | where {$_.EventType == “error”}

> The syntax is:   
> Table_name | search “search term”  
>   
> Note: There are several versions of this question in the exam. The question has three possible correct answers:  
1. search in (Event) “error”
2. Event | search “error”
3. Event | where EventType == “error”

## Topic2/Question23
You have an Azure subscription that contains a virtual network named VNET1 in the East US 2 region. A network interface named VM1-NI is connected to VNET1.
You **successfully deployed** the following Azure Resource Manager template.

![](AZ104%20dump/40F01695-A068-4BDB-B4BF-89668013BD75%2017.png)

![](AZ104%20dump/918353B4-5544-499D-9808-8B6D2143AF10%2019.png)

## Topic2/Question24
You have an Azure subscription named Subscription1. Subscription1 contains the resource groups in the following table.
![](AZ104%20dump/92A2D270-3117-49FA-AC07-6F4265CD4673%2019.png)

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
- Can be assigned only to the resource groups in Subscription1
- Prevents the management of the access permissions for the resource groups
- Allows the viewing, creating, modifying, and deleting of resources within the resource groups

What should you specify in the assignable scopes and the permission elements of the definition of CR1? To answer, select the appropriate options in the answer area.
![](AZ104%20dump/3A0B61AD-708B-49DB-A9C4-CD3CD04878B9%2019.png)
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

![](AZ104%20dump/D4ED7406-A7FC-46C1-8C0F-69F05A5833A7%2019.png)


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

## Topic2/Question31
You have an Azure Active Directory (Azure AD) tenant named adatum.com. Adatum.com contains the groups in the following table.

![](AZ104%20dump/E00B0F74-13E0-4C42-96A1-DE0E4F39A01D%2018.png)

You create two user accounts that are configured as shown in the following table.

![](AZ104%20dump/0BF9C25A-F9F3-4AF1-8EDE-6E0040507491%2018.png)

Of which groups are User1 and User2 members? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0008000001%2018.png)

## Topic2/Question32
You have a hybrid deployment of Azure Active Directory (Azure AD) that contains the users shown in the following table.

![](AZ104%20dump/0008100001%2018.png)

You need to modify the JobTitle and UsageLocation attributes for the users.
For which users can you modify the attributes from Azure AD? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0008300001%2022.png)

> Box 1:User1 and User3 only  
> You must use Windows Server Active Directory to update the identity, contact info, or job info for users whose source of authority is Windows Server Active Directory.  
>   
> Box 2: User1, User2, and User3  
> Usage location is an Azure property that can only be modified from Azure AD (for all users including Windows Server AD users synced via Azure AD Connect).  
https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal

## Topic2/Question81
You have a hybrid deployment of Azure Active Directory (Azure AD) that contains the users shown in the following table.

![](AZ104%20dump/image683%205.png)

You need to modify the JobTitle and UsageLocation attributes for the users.

For which users can you modify the attributes from Azure AD? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0008300001%2023.png)
> when <On-Premises Sync Enable> is “YES” that means the user is in the On-prem AD. When the status is “NO” that means the Users is at AZURE AD.  

## Topic2/Question30 
You have an Azure subscription linked to an Azure Active Directory tenant. The tenant includes a user account named User1.
You need to ensure that User1 can assign a policy to the tenant root management group. What should you do?
* A. Assign the Owner role for the Azure Subscription to User1, and then modify the default conditional access policies.
* B. Assign the Owner role for the Azure subscription to User1, and then instruct User1 to configure access management for Azure resources.
* C. Assign the Global administrator role to User1, and then instruct User1 to configure access management for Azure resources. ✔️
* D. Create a new management group and delegate User1 as the owner of the new management group.

> No one is given default access to the root management group. Azure AD Global Administrators are the only users that can elevate themselves to gain access.  

![](AZ104%20dump/468DC18D-D929-43C4-9C47-B5E6232C166D%2019.png)

## Topic2/Question33
You need to ensure that an Azure Active Directory (Azure AD) user named Admin1 is assigned the required role to enable Traffic Analytics for an Azure subscription.
- You assign the Network Contributor role at the subscription level to Admin1. ✔️
- You assign the Owner role at the subscription level to Admin1. ✔️
- You assign the Reader role at the subscription level to Admin1. ✔️

> Your account must have any one of the following Azure roles at the subscription scope:   
> - **owner**  
> - **contributor**  
> - **reader**  
> - **network contributor**  

## Topic2/Question36
You have an Azure subscription that contains a user named User1.
You need to ensure that User1 can **deploy virtual machines and manage virtual networks.** The solution must use the principle of least privilege.
Which role-based access control (RBAC) role should you assign to User1?
* A. Owner
* B. Virtual Machine Contributor
* C. Contributor ✔️
* D. Virtual Machine Administrator Login

> virtual machine 과 virtual network 을 manage 할 수 있어야하기 때문에 Contributor role을 부여해야 함.  

## Topic2/Question37 
You have an Azure Active Directory (Azure AD) tenant that contains three global administrators named Admin1, Admin2, and Admin3.
The tenant is associated to an Azure subscription. Access control for the subscription is configured as shown in the Access control exhibit. (Click the Access Control tab.)
![](AZ104%20dump/0008700001%2017.jpg)

You sign in to the Azure portal as Admin1 and configure the tenant as shown in the Tenant exhibit. (Click the Tenant tab.)
![](AZ104%20dump/70A25E2F-9111-4ED7-AB0C-5031420EAA15%2017.png)

![](AZ104%20dump/A0BAEA74-5215-493B-9201-BFB700175858%2017.png)

> Global Administrator 는 EntraID(AD) 최고권한. Azure 권한/RBAC 와는 다른 권한임에 유의해야 함. Azure portal은 Entra ID로 관리할 수 있는 여러 Azure Services 중 하나일 뿐임. **Global Administrator는 access elevation으로 Azure 자원을 관리할 권한을 가질 수 있음.**  
>   
> 시나리오 권한 설명  
> — Admin1 : Global administrator + User Access Administrator (same as Owner role)  
> — Admin2  : Global administrator Only (no access to Azure resources)  
> — Admin3 : Global administrator + Owner  

## Topic2/Question59
You java an Azure subscription that contains the following users in an Azure AD tenant named contoso.onmiscrosoft.com:

![](AZ104%20dump/D8EB7E8B-B50C-4CB2-B1E2-45FAC889B8EB%208.png)

User1 creates a new Azure AD tenant named external.contoso.onmicrosoft.com. You need to create new user accounts in external.contoso.onmicrosoft.com.

- You instruct User2 to create the user accounts. Does that meet the goal?  No
- You instruct User3 to create the user accounts. Does that meet the goal?  No
- You instruct User4 to create the user accounts. Does that meet the goal?  No


> — external.contoso.onmicrosoft.com  
> User1이 생성한 테넌트로 User1 만이 Owner권한을 가지고 다른 Global Admin들은 신규 테넌트에 Globe access 권한이 없음. (최초 생성자는 Owner role 을 부여 받음)  
> 	* Owner: Full access to all resources. Delegate access to others  
>   
> — contoso.onmiscrosoft.com:  
> Azure AD 의 Global/User Administrator role 을 가진 User1, User2, User3 가 계정 생성 할 수 있음  
> User4는 Azure subscription Owner role 을 가지고 있어 Azure AD에 계정 생성권한은 없지만, Azure resources 관리 권한과 역할 부여 권한을 가지고 있음.  
> 반면, User1, User2, User3은 구독 관련 role 없기 때문에 Azure resources 접근은 불가한 상태.   
> 그러나 Global Administrator 은 스스로 access elevation으로 리소스 접근권한을 가질 수 있음.  

## Topic2/Question64
You have an Azure App Services web app named App1.
You plan to deploy App1 by using Web Deploy.
You need to ensure that the developers of App1 can use their Azure AD credentials to deploy content to App1. The solution must use the principle of least privilege.

What should you do?
* A. Assign the Owner role to the developers 
* B. Configure app-level credentials for FTPS
* C. Assign the Website Contributor role to the developers ✔️
* D. Configure user-level credentials for FTPS

## Topic2/Question38
You have an Azure subscription named Subscription1 that contains an Azure virtual machine named VM1. VM1 is in a resource group named RG1.
VM1 runs services that will be used to deploy resources to RG1.
You need to ensure that a service running on VM1 can manage the resources in RG1 by using the identity of VM1.
What should you do **first**?
* A. From the Azure portal, modify the Managed Identity settings of VM1 ✔️
* B. From the Azure portal, modify the Access control (IAM) settings of RG1
* C. From the Azure portal, modify the Access control (IAM) settings of VM1
* D. From the Azure portal, modify the Policies settings of RG1

> Managed identities provide an identity for applications to use when connecting to resources that support Azure Active Directory (Azure AD) authentication. Once you have enabled Managed Identity for this VM, you can then give it access using IAM.  

## Topic2/Question39
You have an Azure subscription that contains a resource group named TestRG. You use TestRG to validate an Azure deployment.
TestRG contains the following resources:
![](AZ104%20dump/0009100001%2017.png)
You need to delete TestRG.
What should you do first?
* A. Modify the backup configurations of VM1 and modify the resource lock type of VNET1
* B. Remove the resource lock from VNET1 and delete all data in Vault1  ✔️
* C. Turn off VM1 and remove the resource lock from VNET1
* D. Turn off VM1 and delete all data in Vault1

> 1. Remove VM Backup from Recovery Services Vault  
> 	- Stop backup and delete backup data  
> 2. Remove the Delete Lock on vNet  
> 3. Delete the Resource Group  

## Topic2/Question40/DNS
You have an Azure DNS zone named adatum.com.
You need to delegate a subdomain named research.adatum.com to a **different DNS server** in Azure.
What should you do?
* A. Create an NS record named research in the adatum.com zone. ✔️
* B. Create a PTR record named research in the adatum.com zone.
* C. Modify the SOA record of adatum.com.
* D. Create an A record named *.research in the adatum.com zone.

**NS record**
> An NS record or (name server record) tells recursive name servers which name servers are authoritative for a zone. You can have as many NS records as you would like in your zone file. The benefit of having multiple NS records is the redundancy of your DNS service.  

**DNS A 레코드**
> A record stands for Address record. A 레코드의 가장 일반적인 용도는 IP 주소 조회, 즉 도메인 이름(예: “cloudflare.com”)을 IPv4 주소와 일치시키는 것. 예를 들어 cloudflare.com의 DNS 레코드를 끌어오면 A 레코드는 현재 IP 주소 104.17.210.9를 반환함. if we were to ask to use the same dns server for a subdomain, D could have been an option.  

## Topic2/Question43/DNS
You have a registered DNS domain named contoso.com.
You create a public Azure DNS zone named contoso.com.
You need to ensure that records created in the contoso.com zone are resolvable from the internet.
What should you do?
* A. Create NS records in contoso.com.
* B. Modify the SOA record in the DNS domain registrar.
* C. Create the SOA record in contoso.com.
* D. Modify the NS records in the DNS domain registrar. ✔️

> To ensure that records created in the contoso.com zone are resolvable from the internet, you need to modify the NS (Name Server) records in the DNS domain registrar.  
>   
> When you create a public Azure DNS zone named contoso.com, Azure assigns a set of NS records for that zone. These NS records specify the name servers responsible for handling DNS queries for the contoso.com domain. To make the records in the Azure DNS zone resolvable from the internet, you need to update the NS records at the DNS domain registrar to point to the name servers provided by Azure.  

## Topic2/Question40/DNS
You have an Azure Active Directory (Azure AD) tenant that has the contoso.onmicrosoft.com domain name.
You have a domain name of contoso.com registered at a third-party registrar.
You need to ensure that you can create Azure AD users that have names containing a suffix of @contoso.com.
Which three actions should you perform in sequence? 
![](AZ104%20dump/3C70DC05-A84E-486E-A794-849AFF295C5D%2017.png)

## Topic2/Question44
You have an Azure subscription that contains a storage account named storage1. The subscription is linked to an Azure Active Directory (Azure AD) tenant named contoso.com that syncs to an on-premises Active Directory domain.
The domain contains the security principals shown in the following table.
![](AZ104%20dump/0009600001%2017.png)
In Azure AD, you create a user named User2.
The storage1 account contains a file share named share1 and has the following configurations.
![](AZ104%20dump/0009600002%2017.png)
For each of the following statements, select Yes if the statement is true. Otherwise, select No.
![](AZ104%20dump/B21351ED-C95E-47CF-8530-EC3B332AE022%2017.png)

> note that Storage File Data SMB Share contributor, Reader and so on is RBAC role. Role Based Access Control of Azure.  
> Azure RBAC is designed to assigned to users, groups, or service principles.  
>   
> user1: hybrid identity  
> user2 : cloud-only identity. the user is completely unknown to the AD and therefor can’t access that share.  
> computer1: Because computer accounts don’t have an identity in Azure AD, you can’t configure Azure role-based access control (RBAC) for them. However, computer accounts can access a file share by using a default share-level permission.  
>   
> In JSON we can see parameter “directoryServiceOptions” has a value “AD” which means **File Share is enabled for authentication to users having session ticket (Kerberos) issued by local Domain Controller**. It means that this file share can be accessed from computers JOINED to AD (OnPrem) and by Users created in OnPrem AD AND Synced to AAD (for RBAC).  
>   
> — **hybrid identity**: user created in AD and synced to Entra ID become a hybrid identity (flow is always from AD to Entra ID)  
> Hybrid identity is accomplished through provisioning and synchronization.   

## Topic2/Question45
You have an Azure subscription named Subscription1 that contains a virtual network VNet1.
You add the users in the following table.

![](AZ104%20dump/0009700003%2017.png)

Which user can perform each configuration? 

![](AZ104%20dump/0009900001%2017.jpg)

## Topic2/Question46
You have the Azure resources shown on the following exhibit.

![](AZ104%20dump/0010000001%2017.jpg)

You plan to track resource usage and prevent the deletion of resources.
To which resources can you apply locks and tags? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0010200001%2017.png)

## Topic2/Question47
You have an Azure Active Directory (Azure AD) tenant.
You plan to delete multiple users by using Bulk delete in the Azure Active Directory admin center.
You need to create and upload a file for the bulk delete.
Which user attributes should you include in the file?
* A. The user principal name and usage location of each user only
* B. The user principal name of each user only ✔️
* C. The display name of each user only
* D. The display name and usage location of each user only
* E. The display name and user principal name of each user only

> To perform a bulk delete of users in Azure Active Directory, you need to create and upload a CSV file that contains the list of users to be deleted. The file should include the user principal name (UPN) of each user only  

## Topic2/Question49
You need to ensure that an Azure Active Directory (Azure AD) user named Admin1 is assigned the required role to enable Traffic Analytics for an Azure subscription.
- You assign the **Traffic Manager Contributor** role at the subscription level to Admin1. -> No
- Assign **Network Contributor** role at subscription level to Admin1 -> Yes
- Assign **Owner** role at subscription level to Admin1 -> Yes
- Assign **Reader** role at subscription level to Admin1 -> Yes

> Your account must have any one of the following Azure roles at the subscription scope: owner, contributor, reader, or network contributor.  

## Topic2/Question50
You have three offices and an Azure subscription that contains an Azure Active Directory (Azure AD) tenant.
You need to grant user management permissions to a local administrator in each office.
What should you use?
* A. Azure AD roles
* B. administrative units ✔️
* C. access packages in Azure AD entitlement management
* D. Azure roles

> It can be useful to restrict administrative scope by using administrative units in organizations that are made up of independent divisions of any kind.  
>   
> administrative units are Azure AD resource that can be a container for other Azure AD resources. they can have users, groups and devices.  

## Topic2/Question54
You configure the custom role shown in the following exhibit.

![](AZ104%20dump/0011200001%207.png)

![](AZ104%20dump/1978EAB8-3810-41A7-B659-F693B90C8A60%207.png)

![](AZ104%20dump/DCE77554-FEAB-4E05-89B4-4BD2AE43EBB6%207.png)


## Topic2/Question55
You have an Azure subscription that contains a storage account named storage1. The storage1 account contains a file share named share1.
The subscription is linked to a hybrid Azure Active Directory (Azure AD) tenant that contains a **security group** named Group1.
You need to grant Group1 the Storage File Data SMB Share Elevated Contributor role for share1.
What should you do first?
* A. Enable Active Directory Domain Service (AD DS) authentication for storage1. ✔️
* B. Grant share-level permissions by using File Explorer.
* C. Mount share1 by using File Explorer.
* D. Create a private endpoint.

> prerequisites for **Identity-based access** to gain access to a specific file share :  
1. Select or create an Azure AD tenant.
2. To support authentication with Azure AD credentials, you must enable Azure AD Domain Services for your Azure AD tenant.
3. Domain-join an Azure VM with Azure AD DS.
4. Select or create an Azure file share.
5. Verify Azure files connectivity by mounting Azure file shares using your storage account key.

> Note: The Storage File Data SMB Share Elevated Contributor allows read, write, delete and modify NTFS permissions in Azure Storage file shares over SMB.  

## Topic2/Question57
You have an Azure subscription that contains the hierarchy shown in the following exhibit.

![](AZ104%20dump/0011800001%209.png)

You create an Azure Policy definition named Policy1.
To which Azure resources can you assign Policy1 and which Azure resources can you specify as exclusions from Policy1? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0011900002%209.png)

> Note: Azure provides four levels of scope: management groups, subscriptions, resource groups, and resources  
![](AZ104%20dump/0012000001%209.png)


## Topic2/Question61
You have two Azure subscriptions named Sub1 and Sub2.
An administrator creates a custom role that has an assignable scope to a resource group named RG1 in Sub1.
You need to ensure that you can **apply the custom role to any resource group in Sub1 and Sub2**. The solution must minimize administrative effort.
What should you do?
* A. Select the custom role and add Sub1 and Sub2 to the assignable scopes. Remove RG1 from the assignable scopes. ✔️
* B. Create a new custom role for Sub1. Create a new custom role for Sub2. Remove the role from RG1.
* C. Create a new custom role for Sub1 and add Sub2 to the assignable scopes. Remove the role from RG1.
* D. Select the custom role and add Sub1 to the assignable scopes. Remove RG1 from the assignable scopes. Create a new custom role for Sub2.

> Can be used as:  
> “AssignableScopes”: [  
> 	“/subscriptions/{Sub1}”,  
> 	“/subscriptions/{Sub2}”  
> ]  


## Topic2/Question65
After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.
You have an Azure Active Directory (Azure AD) tenant named contoso.com.
You have a CSV file that contains the ****names and email addresses**** of 500 external users.
You need to create a guest user account in contoso.com for each of the 500 external users.
- Solution: From Azure AD in the Azure portal, you use the Bulk invite users operation.
Does this meet the goal?

> No , Email address and Redirection url are required for csv bulk upload  

## Topic2/Question66
You have an Azure subscription that is linked to an Azure AD tenant. The tenant contains the custom role-based access control (RBAC) roles shown in the following table.

![](AZ104%20dump/image567%206.png)

From the Azure portal, you need to create two custom roles named Role3 and Role4. Role3 will be an `Azure subscription role`. Role4 will be an `Azure AD role`.
Which roles can you clone to create the new roles? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/D94CC330-EC82-46F1-B3A6-0CD66E0CD56C%206.png)

## Topic2/Question67
You have an Azure subscription named Sub1 that contains two users named User1 and User2.
You need to assign role-based access control (RBAC) roles to User1 and User2. The users must be able to perform the following tasks in Sub1:
* User1 must view the data in any storage account.
* User2 must assign users the Contributor role for storage accounts.

The solution must use the principle of least privilege.
Which RBAC role should you assign to each user? To answer, drag the appropriate roles to the correct users. Each role may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.

![](AZ104%20dump/52EA8847-1A9E-4C6B-A71A-797594FD9C07%206.png)

## Topic2/Question68
You have an Azure subscription that contains 10 virtual machines, a key vault named Vault1, and a network security group (NSG) named NSG1. All the resources are deployed to the East US Azure region.

The virtual machines are protected by using NSG1. NSG1 is configured to block all outbound traffic to the internet.

You need to ensure that the virtual machines can access Vault1. The solution must use the principle of least privilege and minimize administrative effort.
What should you configure as the destination of the outbound security rule for NSG1?
* A. an application security group
* B. a service tag ✔️
* C. an IP address range

![](AZ104%20dump/BD92A9BC-901D-4344-88D4-44D027BB43F8%205.png)
![](AZ104%20dump/8F462051-A34C-4C8B-AF09-2C5208AF312F%205.png)

> “AzureKeyVault” tag can be used in outbound NSGs.  
>   
> A service tag represents a group of IP address prefixes from a given Azure service. Microsoft manages the address prefixes encompassed by the service tag and automatically updates the service tag as addresses change, minimizing the complexity of frequent updates to network security rules.  
>   
> You can use service tags to define network access controls on  [network security groups](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview#security-rules) ,  [Azure Firewall](https://learn.microsoft.com/en-us/azure/firewall/service-tags) , and user-defined routes. Use service tags in place of specific IP addresses when you create security rules and routes.   

## Topic2/Question69
You have an Azure AD tenant named adatum.com that contains the groups shown in the following table.

![](AZ104%20dump/image572%205.png)

Adatum.com contains the users shown in the following table.

![](AZ104%20dump/image573%205.png)

You assign the Azure Active Directory Premium Plan 2 license to Group1 and User4.
Which users are assigned the Azure Active Directory Premium Plan 2 license?
* A. User4 only
* B. User1 and User4 only ✔️
* C. User1, User2, and User4 only
* D. User1, User2, User3, and User4

> Under Limitations and known issues:  
> Group-based licensing currently does not support groups that contain other groups (nested groups). If you apply a license to a nested group, only the immediate first-level user members of the group have the licenses applied.  

## Topic2/Question70
You have an Azure AD tenant named contoso.com.
You have two external partner organizations named fabrikam.com and litwareinc.com. Fabrikam.com is configured as a connected organization.
You create an access package as shown in the Access package exhibit. (Click the Access package tab.)

![](AZ104%20dump/image574%205.png)

You configure the external user lifecycle settings as shown in the Lifecycle exhibit. (Click the Lifecycle tab.)

![](AZ104%20dump/image575%205.png)

For each of the following statements, select Yes if the statement is true. Otherwise, select No.
![](AZ104%20dump/image576%205.png)
- NNY

> Litwareinc.com is not connected organization.  
> After 365 days, fabrikam.com users will be blocked from signing in.   


## Topic2/Question72
You have an Azure subscription that contains the users shown in the following table.

![](AZ104%20dump/image627%205.png)

The groups are configured as shown in the following table.

![](AZ104%20dump/image628%205.png)

You have a resource group named RG1 as shown in the following exhibit.

![](AZ104%20dump/image629%205.png)


![](AZ104%20dump/image631%205.png)

## Topic2/Question74
Your on-premises network contains a VPN gateway.
You have an Azure subscription that contains the resources shown in the following table.

![](AZ104%20dump/image646%205.png)

You need to ensure that all the traffic from VM1 to storage1 **travels across the Microsoft backbone network.**
What should you configure?
* A. Azure Application Gateway
* B. private endpoints ✔️
	* or service endporints
* C. a network security group (NSG)
* D. Azure Virtual WAN

> To ensure that all the traffic from VM1 to storage1 travels across the Microsoft backbone network without going out to the public internet, you should use a private endpoint.  
>   
> A private endpoint uses a private IP address from your VNet, effectively bringing the service into your VNet. Any traffic between your virtual machine and the storage account will traverse over the VNet and stay on the Microsoft backbone network, without ever leaving it.  

## Topic2/Question75
You have an Azure subscription that contains a user named User1 and the resources shown in the following table.

![](AZ104%20dump/image647%205.png)

NSG1 is associated to networkinterface1.
User1 has role assignments for NSG1 as shown in the following table.

![](AZ104%20dump/image648%205.png)

For each of the following statements, select Yes if the statement is true. Otherwise, select No.

![](AZ104%20dump/image650%205.png)

![](AZ104%20dump/5F41D52C-5F4E-4C0C-B9D8-9703334269E6%205.png)

## Topic2/Question77
You have three Azure subscriptions named Sub1, Sub2, and Sub3 that are linked to an Azure AD tenant.

The tenant contains a user named User1, a security group named Group1, and a management group named MG1. User is a member of Group1.

Sub1 and Sub2 are members of MG1. Sub1 contains a resource group named RG1. RG1 contains five Azure functions.

You create the following role assignments for MG1:
* Group1: Reader
* User1: User Access Administrator

**You assign User1 the Virtual Machine Contributor role for Sub1 and Sub2.**

![](AZ104%20dump/image656%205.png)
> user1 은 virtual machine contributor 로 새로운 resource group을 생성할 권한이 없음. 그래서 기존 resource group 에만 vm을 manage 할 수 있음.  
![](AZ104%20dump/DC2FEA9D-B4F2-4F47-86B8-684501C28F56%205.png)

## Topic2/Question78
You have an Azure subscription that contains the resources shown in the following table.

![](AZ104%20dump/image657%205.png)

You need to assign User1 the Storage File Data SMB Share Contributor role for share1.

What should you do first?
* A. Enable identity-based data access for the file shares in storage1. ✔️
* B. Modify the security profile for the file shares in storage1.
* C. Select Default to Azure Active Directory authorization in the Azure portal for storage1.
* D. Configure Access control (IAM) for share1.

## Topic2/Question86/Azure Storage
You have an Azure Storage account named storage1 that uses Azure Blob storage and Azure File storage.

You need to use AzCopy to copy data to the blob storage and file storage in storage1.

Which authentication method should you use for each type of storage? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/image692%205.png)

![](AZ104%20dump/539F131A-1C09-4472-8C3F-10537C602F32%204.png)

## Topic3/Question24/Azure Storage
You have an Azure Storage account named storage1.
You plan to use AzCopy to copy data to storage1.
You need to identify the storage services in storage1 to which you can copy the data.
Which storage services should you identify?
* A. blob, file, table, and queue
* B. blob and file only ✔️
* C. file and table only
* D. file only
* E. blob, table, and queue only

> AzCopy is common-line utility that we can use to copy blobs or files to or from a storage account.  

## Topic3/Question25/Azure Storage
You have an Azure Storage account named storage1 that uses Azure Blob storage and Azure File storage.
You need to use AzCopy to copy data to the blob storage and file storage in storage1.
Which authentication method should you use for each type of storage? To answer, select the appropriate options in the answer area.
![](AZ104%20dump/0018700001%203.png)

- Box 1: Both Azure Active Directory (AD) and Shared Access Signature (SAS) token are supported for Blob storage.
- Box 2: Only Shared Access Signature (SAS) token is supported for File storage.

> You can provide authorization credentials by using Azure Active Directory (AD), or by using a Shared Access Signature (SAS) token.  

## Topic3/Question26/Azure Storage
You have an Azure subscription that contains an Azure Storage account.
You plan to create an Azure container instance named container1 that will use a Docker image named Image1. Image1 contains a Microsoft SQL Server instance that requires persistent storage.
You need to configure a storage service for Container1.
What should you use?
* A. Azure Files ✔️
* B. Azure Blob storage
* C. Azure Queue storage
* D. Azure Table storage

> Azure Container Instances are stateless, which means when restarted, crashes, or stops, all of its state is lost. To persist state beyond the lifetime of container, you must mount a volume from Azure file share created with Azure Files.  

## Topic3/Question32/Azure Storage
You have an Azure subscription that contains the storage accounts shown in the following exhibit.
![](AZ104%20dump/0019600001%203.png)

Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.
![](AZ104%20dump/0019700001%203.png)

- Box1: contoso104 only
- Box2: contoso101, contoso102, and contoso103
	- Access tier is supported for blob data.
	- Hot > Cool > Cold > Archive tier
	- File Storage does not support blob data.
![](AZ104%20dump/30A691EE-F21D-43C0-9DFB-2243BEF88BAE%203.png)

## Topic3/Question42/Azure Storage
You have an Azure Storage account named storage1 that contains a blob container. The blob container has a default access tier of Hot. Storage1 contains a container named container1.
You create lifecycle management rules in storage1 as shown in the following table.
![](AZ104%20dump/0020800001%202.png)

You perform the actions shown in the following table.
![](AZ104%20dump/0020900001%202.png)

For each of the following statements, select Yes if the statement is true. Otherwise, select No.

![](AZ104%20dump/0020900002%202.jpg)

- NYY

![](AZ104%20dump/D8467396-C949-4657-A49B-E8AD65A836B5%202.png)


## Topic3/Question44/Azure Storage
You have an Azure Storage account named storage1 that stores images.
You need to create a new storage account and replicate the images in storage1 to the new account by using object replication.
How should you configure the new account?

![](AZ104%20dump/0021100001%202.jpg)

- Box1: StorageV2 or BlobStorage only
- Box2: Container

> object replication is supported for general-purpose v2 storage accounts and premium block blob accounts.  

## Topic3/Question47/Azure Storage
You have an Azure subscription that contains the storage accounts shown in the following table.
![](AZ104%20dump/0020200001%202.png)

You plan to manage the data stored in the accounts by using lifecycle management rules.
To which storage accounts can you apply lifecycle management rules?
* A. storage1 only
* B. storage1 and storage2 only
* C. storage3 and storage4 only
* D. storage1, storage2, and storage3 only ✔️
* E. storage1, storage2, storage3, and storage4

> Lifecycle management policies are supported for  
> - general-purpose v2  
> - premium block blob  
> - blob storage accounts  

## Topic3/Question40/Azure Storage
You have an Azure subscription that contains a storage account named storage1.
You have the devices shown in the following table.
![](AZ104%20dump/0020700001%203.png)
From which devices can you use AzCopy to copy data to storage1?
* A. Device 1 only
* B. Device1, Device2 and Device3 ✔️
* C. Device1 and Device2 only
* D. Device1 and Device3 only

![](AZ104%20dump/892339FE-4AEF-4FDA-BD73-62A301F8E967%203.png)

## Topic3/Question45/Azure Storage
You have an on-premises server that contains a folder named D:\Folder1.
You need to copy the contents of D:\Folder1 to the public container in an Azure Storage account named contosodata.
Which command should you run?
* A. https://contosodata.blob.core.windows.net/public
* B. azcopy sync D:\folder1 https://contosodata.blob.core.windows.net/public --snapshot
* C. azcopy copy D:\folder1 https://contosodata.blob.core.windows.net/public --recursive ✔️
* D. az storage blob copy start-batch D:\Folder1 https://contosodata.blob.core.windows.net/public

## Topic3/Question47/Azure Storage
You have an Azure subscription that contains the storage accounts shown in the following table.
![](AZ104%20dump/0021400001%203.png)
You plan to use AzCopy to copy a blob from container1 directly to share1.
You need to identify which authentication method to use when you use AzCopy. What should you identify for each account? 

![](AZ104%20dump/0021500001%203.jpg)

- Box1: SAS token
- Box2: SAS token

![](AZ104%20dump/539F131A-1C09-4472-8C3F-10537C602F32%205.png)

## Topic2/Question88
You have an Azure subscription that contains the resources shown in the following table.

![](AZ104%20dump/image695%205.png)

You need to assign Workspace1 a role to allow read, write, and delete operations for the data stored in the containers of storage1.
Which role should you assign?
* A. Storage Account Contributor
* B. Contributor
* C. Storage Blob Data Contributor ✔️
* D. Reader and Data Access

## Topic3/Question43
You are configuring Azure Active Directory (Azure AD) authentication for an Azure Storage account named storage1.
You need to ensure that the members of a group named Group1 can upload files by using the Azure portal. The solution must use the principle of least privilege.
Which two roles should you configure for storage1? Each correct answer presents part of the solution.
* A. Storage Account Contributor 
* B. Storage Blob Data Contributor ✔️
* C. Reader ✔️
* D. Contributor
* E. Storage Blob Data Reader

> To Browse the Storage Account in Azure Portal, the Reader role is required.  
> The Reader role is an Azure Resource Manager role that permits users to view storage account resources.  
>   
> Storage Account Contributor has no DataActions, thus no ability to upload any files.  

![](AZ104%20dump/68B7638E-E73A-406F-A113-A66B4C8B36D1%203.png)


## Topic2/Question91
You have an Azure AD tenant.
You need to create a Microsoft 365 group that contains only members of a marketing department in France.

How should you complete the dynamic membership rule? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/image698%204.png)

## Topic3/Question2
You have Azure Storage accounts as shown in the following exhibit.
![](AZ104%20dump/0014100001%204.jpg)
Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.

![](AZ104%20dump/0014200001%204.jpg)

![](AZ104%20dump/0014200002%204.jpg)

## Topic3/Question4
You have an Azure Storage account named storage1.
You have an Azure App Service app named App1 and an app named App2 that runs in an Azure container instance. Each app uses a managed identity.
You need to ensure that App1 and App2 can read blobs from storage1. The solution must meet the following requirements:
- ✑ Minimize the number of secrets used.
- ✑ Ensure that App2 can only read from storage1 for the next 30 days.

What should you configure in storage1 for each app? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0014500001%204.jpg)

- Box 1: Access Control (IAM)
Since the App1 uses Managed Identity, App1 can access the Storage Account via IAM. As per requirement, we need to minimize the number of secrets used, thus Access keys is not ideal.

- Box 2: Shared access signatures (SAS)
We need temporary access for App2, so we need to use SAS.
Shared Access Signature(SAS) is a URI that grants restricted rights to Azure storage resources. by distributing a SAS URI to these clients, you grants then access to a resource for a specified period of time.

## Topic3/Question5
You need to create an Azure Storage account that meets the following requirements:
- ✑ Minimizes costs
- ✑ Supports hot, cool, and archive blob tiers
- ✑ Provides fault tolerance if a disaster affects the Azure region where the account resides

How should you complete the command? To answer, select the appropriate options in the answer area.
Hot Area:
![](AZ104%20dump/0014700004%204.jpg)

![](AZ104%20dump/0014800001%204.jpg)

- General Purpose v1 (GPv1) accounts do not support tiering, while General Purpose v2 (GPv2) accounts do.

- Geo-redundant storage (GRS): Cross-regional replication to protect against region-wide unavailability.
- Locally-redundant storage (LRS): A simple, low-cost replication strategy. Data is replicated within a single storage scale unit.
- Read-access geo-redundant storage (RA-GRS): Cross-regional replication with read access to the replica. RA-GRS provides read-only access to the data in the secondary location, in addition to geo-replication across two regions, but is more expensive compared to GRS.

## Topic3/Question7
You have an Azure subscription that contains the resources shown in the following table.

![](AZ104%20dump/0015000001%204.png)

The status of VM1 is Running.
You assign an Azure policy as shown in the exhibit. (Click the Exhibit tab.)
![](AZ104%20dump/0015100001%204.jpg)

You assign the policy by using the following parameters:
- Microsoft.ClassicNetwork/virtualNetworks
- Microsoft.Network/virtualNetworks
- Microsoft.Compute/virtualMachines
For each of the following statements, select Yes if the statement is true. Otherwise, select No.

![](AZ104%20dump/0015200001%204.png)

- No - You cannot move a resource into a RG if the resource is restricted in the destination RG
- No - The VM will not become deallocated, it will instead be marked as non-compliant
- No

> Policies don’t make changes. They only mark already existing resources as non-compliant unless you setup a remediation which is not done by default  

## Topic3/Question10
You have an Azure subscription named Subscription1.
You create an Azure Storage account named contosostorage, and then you create a file share named data.
Which UNC path should you include in a script that references files from the data file share? To answer, drag the appropriate values to the correct targets. 

![](AZ104%20dump/0015700001%204.jpg)

![](AZ104%20dump/0015800001%204.jpg)

## Topic3/Question11
You have an Azure subscription that contains an Azure Storage account.
You plan to copy an on-premises virtual machine image to a container named vmimages.
You need to create the container for the planned image.
Which command should you run? 

![](AZ104%20dump/0016000001%204.png)

![](AZ104%20dump/0016100001%204.png)
- Similar to OS Images, a VM Image is a collection of metadata and pointers to a set of VHDs (one VHD per disk) stored as page blobs in Azure Storage.

## Topic3/Question16
You have an Azure subscription that contains a storage account named account1.
You plan to upload the disk files of a virtual machine to account1 from your on-premises network. The on-premises network uses a public IP address space of 131.107.1.0/24.
You plan to use the disk files to provision an Azure virtual machine named VM1. VM1 will be attached to a virtual network named VNet1. VNet1 users an IP address space of 192.168.0.0/24.

 You need to configure account1 to meet the following requirements:
- ✑ Ensure that you can upload the disk files to account1.
- ✑ Ensure that you can attach the disks to VM1.
- ✑ Prevent all other access to account1.
Which two actions should you perform? Each correct answer presents part of the solution.

* A. From the Networking blade of account1, select Selected networks. ✔️
* B. From the Networking blade of account1, select Allow trusted Microsoft services to access this storage account.
* C. From the Networking blade of account1, add the 131.107.1.0/24 IP address range. ✔️
* D. From the Networking blade of account1, add VNet1.
	* can be an answer if asked for three actions.
* E. From the Service endpoints blade of VNet1, add a service endpoint.

## Topic3/Question15/StorageRedundancy
You have an Azure subscription that contains the storage accounts shown in the following table.
![](AZ104%20dump/0016900001%204.png)
You need to identify which storage account can be converted to zone-redundant storage (ZRS) replication by requesting a live migration from Azure support.
What should you identify?
* A. storage1 
* B. storage2 ✔️
* C. storage3
* D. storage4

> ZRS currently supports standard general-purpose v2, FileStorage and BlockBlobStorage storage account types.  
![](AZ104%20dump/D41838F1-0B77-4D74-89F6-11D56AE0332A%203.png)
![](AZ104%20dump/68653C04-3CDC-4546-A8AB-F9E3B15762C9%203.png)

## Topic3/Question18/StorageRedundancy
You plan to create an Azure Storage account in the Azure region of East US 2. You need to create a storage account that meets the following requirements:
- ✑ Replicates synchronously.
- ✑ Remains available if a single data center in the region fails.

How should you configure the storage account? To answer, select the appropriate options in the answer area.
![](AZ104%20dump/0017400003%204.png)

![](AZ104%20dump/0017500001%204.png)

- **ZRS supported by StorageV2**

## Topic3/Question35/StorageRedundancy
You have a general-purpose v1 Azure Storage account named storage1 that uses locally-redundant storage (LRS).
You need to ensure that the data in the storage account is protected if a zone fails. The solution must minimize costs and administrative effort.
What should you do first?
* A. Create a new storage account.
* B. Configure object replication rules.
* C. Upgrade the account to general-purpose v2. ✔️
* D. Modify the Replication setting of storage1.

## Topic3/Question46/StorageRedundancy
You have an Azure subscription.
In the Azure portal, you plan to create a storage account named storage1 that will have the following settings:
- ✑ Performance: Standard
- ✑ Replication: Zone-redundant storage (ZRS)
- ✑ Access tier (default): Cool
- ✑ Hierarchical namespace: Disabled
You need to ensure that you can set Account kind for storage1 to BlockBlobStorage.
Which setting should you modify first?
* A. Performance  ✔️
* B. Replication
* C. Access tier (default)
* D. Hierarchical namespace

## Topic3/Question66/StorageRedundancy
You plan to create an Azure Storage account named storage1 that will contain a file share named share1.

You need to ensure that share1 can support SMB Multichannel. The solution must minimize costs.
How should you configure storage?
* A. Premium performance with locally-redundant storage (LRS) ✔️
* B. Standard performance with zone-redundant storage (ZRS)
* C. Premium performance with geo-redundant storage (GRS)
* D. Standard performance with locally-redundant storage (LRS)

> SMB 다중 채널은 네트워크 성능과 파일 서버의 가용성을 향상시키는 SMB(서버 메시지 블록) 3.0 프로토콜의 일부입니다. SMB 다중 채널을 사용하면 파일 서버에서 여러 네트워크 연결을 동시에 사용할 수 있습니다. SMB 3.0 클라이언트와 SMB 3.0 서버 간에 여러 경로를 사용할 수 있는 경우 네트워크 대역폭 및 네트워크 내결함성을 쉽게 집계할 수 있습니다.   
>   
> **SMB Multichannel is available in Premium file shares. LRS/ZRS**  


## Topic3/Question23/StorageRedundancy
You have an Azure subscription.
You create the Azure Storage account shown in the following exhibit.
![](AZ104%20dump/0018300001%203.jpg)
Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.

![](AZ104%20dump/0018400001%203.png)
- Box1: 3
- Box2: Access tier

- in LRS: “Three” Copies in “Three” Racks in a “Single” Datacenter
- in ZRS: “Three” Copies in “Three” Datacenters in a “Single” Region
- Access tier has the “cool” option to store infrequently accessed data. To reduce the cost of infrequently accessed data in the storage account, you must modify the “Access tier (default)” setting.

## AzureFileSync/Question1
You have Azure subscription that includes following Azure file shares:
![](AZ104%20dump/0015500001%204.png)

You have the following on-premises servers:
![](AZ104%20dump/0015500002%204.png)

you create a **Storage Sync Service** named Sync1 and an **Azure File Sync Group** named Group1. Group1 uses shares1 as a **cloud endpoint**. You register Server1 and Server2 in Sync1. You add D:\Folder1 on Server1 as a **server endpoint** of Group1.
![](AZ104%20dump/0015600001%204.jpg)

- Box 1: No
A sync group contains one cloud endpoint, or Azure file share, and at least one server endpoint.
- Box 2: No
Azure File Sync does not support more than one server endpoint from the same server in the same Sync Group.
- Box 3: Yes
Multiple server endpoints can exist on the same volume if their namespaces are not overlapping (for example, F:\sync1 and F:\sync2) and each endpoint is syncing to a unique sync group.
![](AZ104%20dump/254ADF06-1536-4940-8AAA-BE4ABF243BE0%204.png)

## Topic3/Question17/AzureFileSync
You have an on-premises file server named Server1 that runs Windows Server 2016. You have an Azure subscription that contains an Azure file share. You deploy an **Azure File Sync Storage** Sync Service, and you create a sync group. You need to synchronize files from Server1 to Azure. 
Which three actions should you perform in sequence?

![](AZ104%20dump/0017200001%204.png)

1. Prepare Windows Server to use with Azure File Sync
2. Deploy the Storage Sync Service
3. Install the Azure File Sync agent
4. Register Windows Server with Storage Sync Service
5. Create a sync group and a cloud endpoint
6. Create a server endpoint
7. Configure firewall and virtual network settings

## Topic3/Question29/AzureFileSync
You have an Azure subscription that contains an Azure file share. You have an on-premises server named Server1 that runs Windows Server 2016. You plan to set up Azure File Sync between Server1 and the Azure file share. You need to prepare the subscription for the planned Azure File Sync.
Which two actions should you perform?
![](AZ104%20dump/0019100001%203.png)

## Topic3/Question6/AzureFileSync
You have an Azure subscription that contains the resources in the following table.
![](AZ104%20dump/0014900001%204.png)
Store1 contains a file share named data. Data contains 5,000 files.
You need to synchronize the files in the file share named data to an on-premises server named Server1.
Which three actions should you perform? Each correct answer presents part of the solution.

* A. Create a container instance 
* B. Register Server1 ✔️
* C. Install the Azure File Sync agent on Server1 ✔️
* D. Download an automation script
* E. Create a sync group ✔️

## Topic3/Question12/AzureFileSync
You have an Azure File sync group that has the endpoints shown in the following table.
![](AZ104%20dump/0016100002%204.png)
Cloud tiering is enabled for Endpoint3.
You add a file named File1 to Endpoint1 and a file named File2 to Endpoint2.
On which endpoints will File1 and File2 be available **within 24 hours** of adding the files? To answer, select the appropriate options in the answer area.
![](AZ104%20dump/0016200001%204.jpg)

- File1: Endpoint1 only
It is a cloud endpoint, and it is scanned by the detection job every 24 hours.

- File2: Endpoint1, Endpoint2 and Endpoint3
With the on-premises servers the file is scanned and synced automatically after it’s being added.

> Note: server endpoint > immediately added, cloud endpoint > scanned to be added every 24hrs  
> They changed the question in Exam from “within 24 hours” to “after 24 hours”. So, the answer is:  
- File1: Endpoint1, Endpoint2 and Endpoint3
- File2: Endpoint1, Endpoint2 and Endpoint3

## Topic3/Question30/AzureFileSync
You have an Azure subscription that contains the file shares shown in the following table.
![](AZ104%20dump/0019200001%203.png)

You have the on-premises file shares shown in the following table.
![](AZ104%20dump/0019200002%203.png)

You create an Azure file sync group named Sync1 and perform the following actions:
- ✑ Add share1 as the cloud endpoint for Sync1.
- ✑ Add data1 as a server endpoint for Sync1.
- ✑ Register Server1 and Server2 to Sync1.
For each of the following statements, select Yes if the statement is true. Otherwise, select No.

![](AZ104%20dump/0019300001%203.jpg)

![](AZ104%20dump/B44D6130-9E35-4E59-A86B-E9F4D8BF3B22%203.png)
- sync group can have only 1 cloud endpoint and multiple server endpoints.
- data3 can not be a server endpoint since it is not registered.

## Topic3/Question14/AzureFileSync
You have a sync group named Sync1 that has a cloud endpoint. The cloud endpoint includes a file named File1.txt.
Your on-premises network contains servers that run Windows Server 2016. The servers are configured as shown in the following table.

![](AZ104%20dump/0016700001%203.png)

You add Share1 as an endpoint for Sync1. One hour later, you add Share2 as an endpoint for Sync1.
For each of the following statements, select Yes if the statement is true. Otherwise, select No.

![](AZ104%20dump/0016700002%203.jpg)

- NNY
- Azure File Sync never overrides any files on endpoint

## Azure Import/Question1
you have an Azure subscription named Subscription1 that contains the storage accounts shown in the following table:

![](AZ104%20dump/7431EE03-F8CD-4898-B203-D48C9FD426B1%204.png)

you plan to use the Azure Import/Export service to export data from Subscription1. You need to identify which storage account can be used to export the data.
what should you identify?
A. storage1
B. storage2
B. storage3
B. storage4  ✔️

![](AZ104%20dump/0401CCE2-D4A5-497E-91FB-8E9ED003FCFD%204.png)

## Azure Import/Export/Question1
You have Azure subscription that includes data in following locations:

![](AZ104%20dump/99FCB776-4232-40FA-A22A-2F2814C64660%204.png)

You plan to export data by using Azure import/export job named Export1.
You need to identify the data that can be exported by using Export1.
which data should you identify?

A. DB1
B. container1 ✔️
C. share1
D. Table1

## Azure Import/Export/Question3
You have an Azure subscription that contains a storage account. You have an on-premises server named Server1 that runs Windows Server 2016. Sever 1 has 2 TB of data. You need to transfer the data to the storage account by using the Azure Import/Export service. In which order should you perform the actions?

![](AZ104%20dump/0011400001%203.png)

- 1 > 2 > 3 > 4

- Step 1: Prepare the drives
* Step 2: Create an import job
* Step 3: Ship the drives to Azure datacenter
* Step 4: Update the job with tracking information
* Step 5: Verify data upload to Azure


## Topic3/Question19/Azure Import/Export
You plan to user the Azure Import/Export service to copy files to a storage account. Which 2 files should you create before you prepare the drives for the import job?
- A. an XML manifest file
- B. a dataset CSV file ✔️
- C. a JSON configuration file
- D. a PowerShell PS1 file
- E. a driveset CSV file ✔️

## Topic3/Question22/Azure Import/Export
You have an Azure subscription named Subscription1.
You have 5 TB of data that you need to transfer to Subscription1.
You plan to use an Azure Import/Export job.
What can you use as the destination of the imported data?
* A. a virtual machine
* B. an Azure Cosmos DB database
* C. Azure File Storage ✔️
	* or Azure Blob Storage
* D. the Azure File Sync Storage Sync Service

> Azure Import/Export service is used to securely import large amounts of data to Azure Blob storage and Azure Files by shipping disk drives to an Azure datacenter. The maximum size of an Azure Files Resource of a file share is 5 TB.  

## Topic3/Question21/RecoveryServiceVault
You have an Azure subscription named Subscription1 that contains the resources shown in the following table.
![](AZ104%20dump/0017800001%204.png)
In storage1, you create a blob container named blob1 and a file share named share1.
Which resources can be backed up to Vault1 and Vault2? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0017900001%204.png)

- Box 1: VM1 only
VM1 is in the same region as Vault1. File1 is not in the same region as Vault1. SQL is not in the same region as Vault1. Blobs cannot be backup up to service vaults.
Note: To create a Vault to protect VMs, the Vault must be in the same Region as the VMs.
- Box 2: Share1 only
Storage1 is in the same region as Vault2. Share1 is in Storage1.
**Note: Only VM and Fileshare is allowed to back up.**

## Topic3/Question34/RecoveryServiceVault
You have two Azure virtual machines named VM1 and VM2. You have two Recovery Services vaults named RSV1 and RSV2.
VM2 is backed up to RSV1.
You need to back up VM2 to RSV2.
What should you do first?
* A. From the RSV1 blade, click Backup items and stop the VM2 backup ✔️
* B. From the RSV2 blade, click Backup. From the Backup blade, select the backup for the virtual machine, and then click Backup
* C. From the VM2 blade, click Disaster recovery, click Replication settings, and then select RSV2 as the Recovery Services vault
* D. From the RSV1 blade, click Backup Jobs and export the VM2 job

1. Stop the backup in RSV1 (D)
2. Remove the backup data.
3. Disassociate the VM in RSV1.
4. Associate the VM in RSV2.

## RecoveryServiceVault
You have two Azure virtual machines named VM1 and VM2. You have two Recovery Services vaults named  RSV1 and RSV2. 
VM2 is protected by RSV1. 
You need to use RSV2 to protect VM2. 
What should you do first? 
- A. From the VM2 blade, click Disaster recovery, click Replication settings, and then select RSV2 as the  Recovery Services vault.  ✔️
- B. From the RSV2 blade, click Backup. From the Backup blade, select the backup for the virtual machine, and  then click Backup 
- C. From the RSV1 blade, click  Backup Jobs and export the VM2 job. 
- D. From the RSV1 blade, click Backup items and stop the VM2 backup. 

## extra/Question6/RecoveryServiceVault
You need to the appropriate sizes for the Azure virtual for Server2. 
What should you do? To answer, select the appropriate options in the answer area. 

![](AZ104%20dump/371B5A0C-3EDA-42FE-A82D-D5BB5DB04635%204.png)


## Topic3/Question20/RecoveryServiceVault
You have a Recovery Service vault that you use to test backups. The test backups contain two protected virtual machines.
You need to delete the Recovery Services vault.
What should you do first?
* A. From the Recovery Service vault, delete the backup data.
* B. Modify the disaster recovery properties of each virtual machine.
* C. Modify the locks of each virtual machine.
* D. From the Recovery Service vault, stop the backup of each backup item. ✔️

## Topic3/Question31/Azure Backup report
You have an Azure subscription named Subscription1 that contains the resources shown in the following table:
![](AZ104%20dump/0019400001%203.png)
You plan to configure Azure Backup reports for Vault1.
You are configuring the Diagnostics settings for the AzureBackupReports log.
Which storage accounts and which Log Analytics workspaces can you use for the Azure Backup reports of Vault1? To answer, select the appropriate options in the answer area.
![](AZ104%20dump/0019500001%203.jpg)

- Box1: storage3 only
	- it resides in the same region as vault1 (West Europe)
- Box2: Analytics1, Analytics2, and Analytics3
	- the location and subscription where this Log Analytics workspace can be created is **independent of the location and subscription where your vaults exist**.

## Topic4/Question40/RecoveryServiceVault
You have an Azure subscription named Subscription1 that contains the resources shown in the following table.
![](AZ104%20dump/0028300005%203.png)
You create virtual machines in Subscription1 as shown in the following table.
![](AZ104%20dump/0028400001%203.png)
You plan to use Vault1 for the backup of as many virtual machines as possible.
Which virtual machines can be backed up to Vault1?
* A. VM1 only
* B. VM3 and VMC only
* C. VM1, VM2, VM3, VMA, VMB, and VMC
* D. VM1, VM3, VMA, and VMC only ✔️
* E. VM1 and VM3 only

> recovery vault 와 동일 region에 생성된 virtual machine, fileshare 만 백업 대상임.   

## Topic6/Question3/RecoveryServiceVault
You have the Azure virtual machines shown in the following table:
![](AZ104%20dump/0053100001%203.png)
You have a Recovery Services vault that protects VM1 and VM2.
You need to protect VM3 and VM4 by using Recovery Services.
What should you do first?
* A. Create a new Recovery Services vault ✔️
* B. Create a storage account
* C. Configure the extensions for VM3 and VM4
* D. Create a new backup policy

## Topic6/Question23/RecoveryServiceVault
You have a Recovery Services vault named RSV1. RSV1 has a backup policy that retains instant snapshots for five days and daily backup for 14 days.
RSV1 performs daily backups of VM1. VM1 hosts a static website that was updated eight days ago.
You need to recover VM1 to a point eight days ago. The solution must **minimize downtime**.
What should you do first?
* A. Deallocate VM1.
* B. Restore VM1 by using the Replace existing restore configuration option.
* C. Delete VM1.
* D. Restore VM1 by using the Create new restore configuration option. ✔️

> This option allows you to keep the existing VM running while restoring a new instance, minimizing downtime for your static website.  

## Topic6/Question6/RecoveryServiceVault
You have an Azure virtual machine named VM1 and a Recovery Services vault named Vault1.
You create a backup policy named Policy1 as shown in the exhibit. 

![](AZ104%20dump/0053600001%203.jpg)

You configure the backup of VM1 to use Policy1 on Thursday, January 1 at 1:00 AM.
You need to identify the number of available recovery points for VM1. How many recovery points are available on January 8 and January 15? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0053700001%203.jpg)

- 6, 8
> daily backup이 5일간 저장되기때문에 4일치 백업을 가지고있음.  

## Topic6/Question49/RecoveryServiceVault
You create a Recovery Services vault backup policy named Policy1 as shown in the following exhibit:

![](AZ104%20dump/image752%203.png)

Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.

![](AZ104%20dump/image753%203.png)

- 10 years and 36 months

## Topic6/Question17/RecoveryServiceVault
You purchase a new Azure subscription named Subscription1.
You create a virtual machine named VM1 in Subscription1. VM1 is not protected by Azure Backup.
You need to protect VM1 by using Azure Backup. Backups must be created at 01:00 and stored for 30 days.
What should you do? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0056200001%203.jpg)

- Box 1: A Recovery Services vault
- Box 2: A backup policy 


## extra/Question2
You need to recommend a solution to automate the configuration for the finance department users. The solution must meet the technical requirements. What should you include in the recommended? 

- A. Azure AP B2C 
- B. Azure AD Identity Protection -
- C. an Azure logic app and the Microsoft Identity Management (MIM) client 
- D. dynamic groups and conditional access policies ✔️

## extra/Question3
- Scenario: Litware must meet technical requirements including: Ensure that VM3 can establish outbound connections over TCP port 8080 to the applications servers in the Montreal office.

You discover that VM3 does NOT meet the technical requirements.
You need to verify whether the issue relates to the NSGs.
What should you use?

* A. Diagram in VNet1
* B. Diagnostic settings in Azure Monitor
* C. Diagnose and solve problems in Traffic Manager profiles
* D. The security recommendations in Azure Advisor
* E. IP flow verify in Azure Network Watcher ✔️

> IP flow verify checks if a packet is allowed or denied to or from a virtual machine. The information consists of direction, protocol, local IP, remote IP, local port, and remote port. If the packet is denied by a security group, the name of the rule that denied the packet is returned.  

## extra/Question4
- Scenario: Connect the New York office to VNet1 over the Internet by using an encrypted connection.

You need to meet the connection requirements for the New York office. What should you do? To answer, select the appropriate options in the answer area.

![](AZ104%20dump/0051100001%204.png)
> A Site-to-Site VPN gateway connection is used to connect your on-premises network to an Azure virtual network over an IPsec/IKE (IKEv1 or IKEv2) VPN tunnel. This type of connection requires a VPN device located on-premises that has an externally facing public IP address assigned to it. Site-to-Site VPN connection requires Virtual network gateway, Local network gateway and Gateway Subnet.  

## extra/Question5
- Scenario: Create a workflow to send an email message when the settings of VM4 are modified. 

You need to meet the technical requirement for VM4.
What should you create and configure?
* A. an Azure Logic App ✔️
* B. an Azure Service Bus
* C. an Azure Notification Hub
* D. an Azure Event Hub 

## extra/Question7
You need to implement Role1. 
Which command should you run before you create Role1? To answer, select the appropriate options in 
the answer area. 

![](AZ104%20dump/AE387826-F81D-44E6-B58E-A69B02F5E1AD%204.png)







