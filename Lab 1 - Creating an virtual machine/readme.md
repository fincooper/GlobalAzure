# Creating an Azure Virtual Machine for Development and Testing

### Scenario

You have elected to use Azure to host a Windows Server 2012 R2 Virtual Machine. In this Virtual Machine, you will install project files, Visual Studio 2015 Community Edition, Azure SDK for .NET and Azure PowerShell. Once complete, you will use this virtual machine for all remaining development tasks.

### Objectives

After you complete this lab, you will be able to:

* Create an affinity group in your Azure subscription.

* Create a virtual network.

* Create a Storage instance.

* Create a virtual machine.

* Manage the virtual machine VHDs.

* Install development software on a virtual machine.

## Exercise 1: Creating a Network and Resource Container

### Scenario

You want to create a virtual network that you can use for your new virtual machine. As part of creating the virtual network, you will also create a resource group.

The main tasks for this exercise are as follows:

1. Sign in to the Azure Portal.

2. Create a virtual network and a resource group.

#### Task 1: Sign in to the Azure Portal

1. Sign in to the Azure Portal (<https://portal.azure.com>).

2. Click **Get Started**.

#### Task 2: Create a Resource Group

1. View the list of resource groups for your subscription.

2. Create a new resource group using the name: **globalazure**.

#### Task 3: Create a Virtual Network

1. View the list of virtual networks for your subscription.

2. Create a virtual network by using the following details:

  - Name: **vnetglobalazure**

  - Location: **West Europe**

  - Existing Resource Group: **globalazure**

  - Address Space: **10.0.0.0/16**

  - Subnet Name: **Apps**

  - Subnet Address Range: **10.0.0.0/24**

> **Results:** After completing this exercise, you will have a new virtual network and resource group in Azure.

## Exercise 2: Creating a Development Virtual Machine

### Scenario

You need a new storage account that you will use while creating your virtual machine. This storage account will contain the VHDs for the virtual machine that you will create.

The main tasks for this exercise are as follows:

1. Create a storage account.

2. Create a virtual machine.

#### Task 1: Create a storage account

1. View the list of Storage instances for your subscription.

2. Create a Storage instance by using the following details:

  - Name: **storglobalazure[Your Name Here]**

  - Deployment model: **Resource manager**

  - Account kind: **General purpose**

  - Performance: **Standard**

  - Replication: **Locally-redundant storage (LRS)**  

  - Resource Group: **globalazure**

  - Location: **West Europe**

#### Task 2: Create a virtual machine

1. View the list of virtual machines for your subscription.

1. Go to the Virtual Machine gallery and select the **Visual Studio Community 2015 Update 3 with Azure SDK 2.9 on Windows Server 2012 R2** template.

2. Create a new virtual machine using the template and the following details:

  - Name: **vmglobalazure**

  - VM disk type: **SSD**

  - User Name: **Student**

  - Password: **AzurePa$$w0rd**

  - Resource Group: **globalazure**

  - Size: **DS1_V2**

  - Storage Account: **storglobalazure[Your Name Here]**
  
  - Virtual Network: **vnetglobalazure**

  - Subnet: **Apps**

  - Boot diagnostics: **Disabled**
    
  - Guest OS diagnostics: **Disabled**

4. Connect to the newly created virtual machine using Remote Desktop.

> **Results:** After completing this exercise, you will have a new virtual machine stored in a new storage account.

## Exercise 3:	Configuring the Virtual Machine for Development

### Scenario

Now that you have a new virtual machine, you need to configure Internet Explorer's Enhanced Security Configuration option. You also need to ensure that your working files are on the machine and ready.

The main tasks for this exercise are as follows:

1. Disable Internet Explorer Enhanced Security Configuration

#### Task 1: Disable IE Enhanced Security Configuration

1. If Server Manager is not already open, open **Server Manager**.

2. Within the *Local Server* configuration screen, disable **Internet Explorer Enhanced Security Configuration** for both *Administrators* and *Users*.

#### Task 2: Add your Azure subscription to Visual Studio

1. Open **Visual Studio 2015**.

2. When prompted, sign-in using the **Microsoft Account** associated with your Azure subscription.

    > **Note:** Ensure that the **Keep me signed in** option is selected when you sign-in.

3. Validate that you can see the Visual Studio **Start Page**.

> **Results:** After completing this exercise, your virtual machine has Visual Studio, Azure PowerShell, and the Azure SDK installed.

©2016 Microsoft Corporation. All rights reserved.  The text in this document is available under the [Creative Commons Attribution 3.0 License](https://creativecommons.org/licenses/by/3.0/legalcode "Creative Commons Attribution 3.0 License"), additional terms may apply.  All other content contained in this document (including, without limitation, trademarks, logos, images, etc.) are **not** included within the Creative Commons license grant.  This document does not provide you with any legal rights to any intellectual property in any Microsoft product. You may copy and use this document for your internal, reference purposes.  
This document is provided "as-is." Information and views expressed in this document, including URL and other Internet Web site references, may change without notice. You bear the risk of using it. Some examples are for illustration only and are fictitious. No real association is intended or inferred. Microsoft makes no warranties, express or implied, with respect to the information provided here.  
