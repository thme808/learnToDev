# AZ104 dump
#개발/Azure

Your company has serval departments. Each department has a number of virtual machines (VMs).
The company has an Azure subscription that contains a resource group named RG1.
All VMs are located in RG1.
You want to associate each VM with its respective department.
What should you do?
* A. Create Azure Management Groups for each department.
* B. Create a resource group for each department.
* **C. Assign tags to the virtual machines.**
* D. Modify the settings of the virtual machines.

Your company has an Azure Active Directory (Azure AD) subscription.
You want to implement an Azure AD conditional access policy.
The policy must be configured to require members of the Global Administrators group to use Multi-Factor Authentication and an Azure AD-joined device when they connect to Azure AD from untrusted locations.

> Solution: **You access the Azure portal to alter the grant control of the Azure AD conditional access policy.**  

Your company’s Azure solution makes use of Multi-Factor Authentication for when users are not in the office. The Per Authentication option has been configured as the usage model.
After the acquisition of a smaller business and the addition of the new staff to Azure Active Directory (Azure AD) obtains a different company and adding the new employees to Azure Active Directory (Azure AD), you are informed that these employees should also make use of Multi-Factor Authentication.
To achieve this, the Per Enabled User setting must be set for the usage model.

> Solution: You **create a new Multi-Factor Authentication provider** with a backup from the existing Multi-Factor Authentication provider data.  

## Topic1/Question9
Your company has an Azure Active Directory (Azure AD) tenant named weyland.com that is configured for hybrid coexistence with the on-premises Active Directory domain.
You have a server named DirSync1 that is configured as a DirSync server.
You create a new user account in the on-premise Active Directory. You now need to replicate the user information to Azure AD immediately.

> Solution: You run the Start-ADSyncSyncCycle -PolicyType Delta PowerShell cmdlet.    
> — delta, initial 둘 다 가능하지만, delta가 더 적합함  

The Start-ADSyncSyncCycle cmdlet has two policy types:
- Delta: This policy type performs a delta (or incremental) synchronization, syncing only the changes since the last sync.
- Initial: This policy type performs a **full synchronization**, syncing all objects and attributes.

## Topic1/Question12
You are configuring the two datacenters as geo-clustered sites for site resiliency.
You need to recommend an Azure storage redundancy option.
You have the following data storage requirements:
✑ Data must be stored on multiple nodes.
✑ Data must be stored on nodes in separate geographic locations.
✑ **Data can be read from the secondary location as well** as from the primary location.
Which of the following Azure stored redundancy options should you recommend?
* A. Geo-redundant storage (GRS)
	* data will be available to be read-only when failover occurs
* B. Read-only geo-redundant storage
	* RA-GRS is correct term (Read Access GRS)
* C. Zone-redundant storage
* D. Locally redundant storage

## Topic1/Question14
Your company has an azure subscription that includes a storage account, a resource group, a blob container and a file share.
A colleague named Jon Ross makes use of a solitary Azure Resource Manager (ARM) template to deploy a virtual machine and an additional Azure Storage account. You want to review the ARM template that was used by Jon Ross.

> Solution: You access the Resource Group blade.  
> Resource Group >> Deployments  

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
> Azure key vault to store the password and Access policy to make it accessible. access policy is considered a legacy way to provide access to the key vault. Now you can use RBAC.  

## Topic1/Question21
Your company has an Azure Active Directory (Azure AD) tenant that is configured for hybrid coexistence with the on-premises Active Directory domain.
The on-premise virtual environment consists of virtual machines (VMs) running on Windows Server 2012 R2 Hyper-V host servers.
You have created some PowerShell scripts to automate the configuration of newly created VMs. You plan to create several new VMs.
You need a solution that ensures the scripts are run on the new VMs.
Which of the following is the best solution?
* A. Configure a SetupComplete.cmd batch file in the %windir%\setup\scripts directory.**Most Voted**
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
![](AZ104%20dump/FF604C05-80CA-4F62-BA72-CE6322278FD3.png)

## Topic1/Question26
Your company’s Azure subscription includes two Azure networks named VirtualNetworkA and VirtualNetworkB.
VirtualNetworkA includes a VPN gateway that is configured to make use of static routing. Also, a site-to-site VPN connection exists between your company’s on- premises network and VirtualNetworkA.
You have configured a point-to-site VPN connection to VirtualNetworkA from a workstation running Windows 10. After configuring virtual network peering between VirtualNetworkA and VirtualNetworkB, you confirm that you are able to access VirtualNetworkB from the company’s on-premises network. However, you find that you cannot establish a connection to VirtualNetworkB from the Windows 10 workstation.
You have to make sure that a connection to VirtualNetworkB can be established from the Windows 10 workstation.
> **Solution: You download and re-install the VPN client configuration package on the Windows 10 workstation.**  

- “After configuring virtual network peering between
VirtualNetworkA and VirtualNetworkB, you confirm that you are able to access VirtualNetworkB from the company’s on-premises network.” This indicates the Allow/Use gateway transit is set up working. The next step will be restart/reinstall the VPN-Client config at the windows 10 workstation.

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

Your company has a Microsoft SQL Server Always On availability group configured on their Azure virtual machines (VMs).
You need to configure an Azure internal load balancer as a listener for the availability group.
> Solution: You enable Floating IP  
- By enabling Floating IP, the load balancer will use a floating IP address as the source IP address for outbound flows from the backend pool. This will ensure that the IP address used by the backend pool remains the same even if a VM is restarted or replaced, which is important for maintaining the listener for the availability group.

## Topic1/Question31
Your company has two on-premises servers named SRV01 and SRV02. Developers have created an application that runs on SRV01. The application calls a service on SRV02 by IP address.
You plan to migrate the application on Azure virtual machines (VMs). You have **configured two VMs on a single subnet in an Azure virtual network**. You need to configure the two VMs with **static internal IP addresses**. What should you do?
* A. Run the New-AzureRMVMConfig PowerShell cmdlet.
* B. Run the Set-AzureSubnet PowerShell cmdlet.
* C. Modify the VM properties in the Azure Management Portal.
* D. Modify the IP properties in Windows Network and Sharing Center.
* E. Run the Set-AzureStaticVNetIP PowerShell cmdlet.**Most Voted**

## Topic1/Question32
Your company has an Azure Active Directory (Azure AD) subscription.
You need to deploy five virtual machines (VMs) to your company’s virtual network subnet.
The VMs will each have both a public and private IP address. Inbound and outbound security rules for all of these virtual machines must be identical.
Which of the following is the least amount of network interfaces needed for this configuration?
* A. 5 ✔️
* B. 10
* C. 20
* D. 40
Which of the following is the least amount of security groups needed for this configuration? 1

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
* C. You should restore the VM to a new Azure VM. **Most Voted**
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
![](AZ104%20dump/932E9687-C584-465F-975B-7C0AF92038FE.png)
-  LB와 backend pool(vm)에 모두에 접근 가능해야함 -> network contributor 역할이**RG level에 할당되어야** 함.
- health probe도 RG레벨에서 접근가능 함
![](AZ104%20dump/AEDC5B4C-D223-491D-BDE1-CAF74C64C1BD.png)

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
![](AZ104%20dump/2308337E-C9E6-4B32-BD5C-3E793D1127B2.png)
User3 is the owner of Group1. Group2 is a member of Group1.
You configure an access review named Review1 as shown in the following exhibit:
![](AZ104%20dump/0F12E6E8-16D7-425C-A8CE-48EDB46105FC.png)

- note that scope is **Guest users only**
- Reviewers are **Group Owners**
![](AZ104%20dump/D85F0920-784C-4CD3-BC73-9838CE863B03.png)

## Topic2/Question5
You have the Azure management groups shown in the following table:
![](AZ104%20dump/55047A69-41C7-425A-9B03-F246EF630DFD.png)
You add Azure subscriptions to the management groups as shown in the following table:
![](AZ104%20dump/F70CC2E5-9178-45DE-8F7C-62709DE0205C.png)
You create the Azure policies shown in the following table:
![](AZ104%20dump/DFE52F83-147F-4D4A-8F36-8D4706FFECFE.png)
![](AZ104%20dump/37214963-CFB4-41CD-9CA4-1B97A6439BA5.png)

## Topic2/Question6
![](AZ104%20dump/F5450418-1B5B-4532-98F4-4ACF92F13D2E.png)
What is the effect of the policy?
* A. You are prevented from creating Azure SQL servers anywhere in Subscription 1.
* B. You can create Azure SQL servers in ContosoRG1 only.
* C. You are prevented from creating Azure SQL Servers in ContosoRG1 only.
* D. You can create Azure SQL servers in any resource group within Subscription 1.

## Topic2/Question7
![](AZ104%20dump/6D2ED933-CF06-4766-A5CB-AE748A2E36FA.png)
- Apply tag and its default value -> Append a tag and its value to resources
- Policy 적용 후에는 tag를 지정하더라도 default tag가 붙음 (아래 VNET3)
- Policy 적용 전 생성된 VNET1은 remediation 해야 default tag 붙음
![](AZ104%20dump/488C37F4-0892-4C86-95E2-DBCFF1C2C7FD.png)

## Topic2/Question8
You have an Azure subscription named AZPT1 that contains the resources shown in the following table:
![](AZ104%20dump/0004900001.png)
You create a new Azure subscription named AZPT2.
You need to identify which resources can be moved to AZPT2.
Which resources should you identify? **ALL**





