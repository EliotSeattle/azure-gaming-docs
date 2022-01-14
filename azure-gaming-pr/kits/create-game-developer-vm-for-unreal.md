---
title: Quickstart - Create a Game Developer Virtual Machine with Unreal Engine
description: Get up and running with a Windows 10 or Server 2019 Game Developer Virtual Machine that has Unreal Engine and other common game development tools pre-installed.
author: dciborow
keywords: 
ms.topic: quickstart
ms.date: 02/01/2022
ms.author: dciborow
ms.prod: azure-gaming
---

# Quickstart: Create a Game Developer Virtual Machine with Unreal Engine

Get up and running with a Windows 10 or Server 2019 Game Developer Virtual Machine that has Unreal Engine and other common game development tools pre-installed.

## Prerequisite

- To create a Game Developer Virtual Machine, you must have an Azure subscription. [Try Azure for free](https://azure.com/free). Please note Azure free accounts do not support GPU enabled virtual machine SKUs.
- An [EPIC account](https://www.epicgames.com/id/login) to accept Epic Games store End User License Agreement after signing in to this VM.
- If you need deploy this VM with Windows 10 as operating system, Multitenant Hosting Rights for Windows 10 is required. See [Subscription Licenses that qualify for Multitenant Hosting Rights](https://docs.microsoft.com/azure/virtual-machines/windows/windows-desktop-multitenant-hosting-deployment#subscription-licenses-that-qualify-for-multitenant-hosting-rights) to verify if you have eligible windows 10 subscription license. You can also deploy Windows 10 in Azure for dev/test scenarios if you have an appropriate [Visual Studio (formerly MSDN) subscription](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
- There are three ways to access this VM: RDP, Teradici or Parsec. If you choose either Teradici or Parsec, you must have your own license ready. Azure will complete the installation of either remote technology in the VM.

## Create your Game Developer VM

To create a Game Dev VM instance:

1. Go to the [Azure portal](https://portal.azure.com/). You might be prompted to sign in to your Azure account if you&#39;re not already signed in.
2. Find the virtual machine listing by typing in &quot;game developer virtual machine&quot; and selecting &quot;xxx&quot;
3. Select the  **Create**  button.
4. You should be redirected to the &quot;Create a virtual machine&quot; blade.
5. Fill in the  **Basics**  tab:

    - **Subscription** : If you have more than one subscription, select the one on which the machine will be created and billed. You must have resource creation privileges for this subscription.
    - **Resource group** : Create a new group or use an existing one.
    - **Region** : Select the datacenter that&#39;s most appropriate. For fastest network access, it&#39;s the datacenter that has most of your existing workloads or is the closest to your physical location. Learn more about [Azure Regions](https://azure.microsoft.com/global-infrastructure/regions/).
    - **VM Size** : This VM currently supports the sizes of [NV](https://docs.microsoft.com/azure/virtual-machines/nv-series), [NVv3](https://docs.microsoft.com/azure/virtual-machines/nvv3-series), and [T4](https://docs.microsoft.com/azure/virtual-machines/nct4-v3-series). Choose a size that is appropriate for your workloads. Read more about [Windows VM sizes in Azure](https://docs.microsoft.com/azure/virtual-machines/sizes).
    - **Virtual machine name** : Enter the name of the virtual machine. This is how it will appear in your Azure portal.
    - **Username** : Enter the administrator username. This is the username you will use to log into your virtual machine, and need not be the same as your Azure username.
    - **Password** : Enter the password you will use to log into your virtual machine. Repeat the same password And **Confirm password** in the next field.
    - **Operating System** : Choose either Windows 10 or Windows Server 2019.

> [!NOTE]
> If you choose Windows 10, you need confirm that you have an eligible license with [multi-tenant hosting rights](https://docs.microsoft.com/azure/virtual-machines/windows/windows-desktop-multitenant-hosting-deployment), unless you want to use this VM for dev/test scenarios if you have an appropriate [Visual Studio (formerly MSDN) subscription](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).

6. Click  **Next: Game Developer Tools**
7. You will see **Select Game Engine.** Select **Unreal Engine Version 4.27** from the dropdown. A list of pre-installed common free game developer tools will show up.

- This VM supports [Unreal Pixel Streaming](https://docs.unrealengine.com/4.27/SharingAndReleasing/PixelStreaming/). You can check the box if you want to enable this feature.
- This VM can be configured to connect Perforce depot if you already have a Perforce Helix Core version control server in place. Check the box **Connect to and sync a Perforce depot** for more configuration if you need this VM connect to Perforce as part of your game development deployment.
- You can select which version of Microsoft Game Development Kit to be included.

1. Click Next: **Remote Access Configuration**
2. Choose RDP, Teradici or Parsec from the **Remote Access Technology** dropdown. If Teradici or Parsec is chosen, you need fill additional licensing information.
3. Click **Next: VM Network**. Under **Configure Public IP and DNS** , and **Configure virtual networks,** you can create new resources, or pick the existing resources, depends on your business needs.
4. Click **Next: Data Storage**.

- From here you can create a disk volume in the VM for data storage that is striped across multiple data disks, which improves the disk throughput. If you don&#39;t want to use the striped disk, please set the number of data disks to be 1. If you don&#39;t want to attach a data disk at all, please set the number to be 0. This VM will still have an OS disk and temporary data disk as the default configuration.
- You can also mount an existing Azure Storage File Share if you have one.

1. Click **Next: Tags**. Tags are used to categorize resources, usually for billing management purpose. For more details, click [here](https://docs.microsoft.com/azure/azure-resource-manager/management/tag-resources?tabs=json). If you don&#39;t need tags now, you can skip this page and click **Next: Review + create**
2. **Review+create**

- Portal will validate whether all the required information has been filled. If any information is missing or incorrect, you will see the validation failed message at the top. You can click **View error details** to know what is causing the error. You will then need go back to complete the missing field(s) or make the correction.
- Once validation is passed, please verify that all the information you entered is correct
- Select  **Create**.

> [!NOTE]
>  
>- There is no additional charge for the software that comes pre-loaded on the virtual machine. You do pay the compute cost for the VM size that you chose in the  **Size**  step. If you choose Teradici or Parsec as your remote access tool, you bring your own license to the VM on Azure.
>- Provisioning takes 10 to 20 minutes. You can view the status of your VM on the Azure portal.

## Access the Game Developer VM

After the VM is created and provisioned, there are three methods to access this VM, depending on the **Remote Access Technology** you chose before.

**Method 1:** RDP. This remote method is always available.

1. Follow the steps listed to [connect and sign on to Azure-based virtual machine](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon). Use the credentials that you configured when created this virtual machine before.
2. Once you sign on to the VM, you&#39;ll be prompted immediately to accept Epic Games store End User License Agreement (EULA) by using your EPIC account. This is a one-time effort. You don&#39;t need repeat this step when you access this VM again.
3. You&#39;re ready to start using the tools that are installed and configured on the VM. Many of the tools can be accessed through Start menu tiles and desktop icons.

**Method 2:** Teradici.

Using through the PCoIP protocol, Teradici connects users to Game Dev VM and delivers a highly responsive, color-accurate, lossless, and distortion-free experience. It is widely used in Media &amp; Entertainment industry with graphics-intensive workloads.

### Remoting into the Game Developer Virtual Machine with Teradici

**Method 3:** Parsec

Parsec is a high performance remote access technology built for Media &amp; Entertainment industry. It provides high fidelity and low latency remote access experience.

Remoting into the Game Developer Virtual Machine with Parsec

Next steps

- Explore the tools on the Game Dev VM by opening the  **Start**  menu.
- Start to learn and use [Unreal Engine](https://www.unrealengine.com/learn).
- Learn about the Game development on Azure by reading [Azure for Gaming](https://docs.microsoft.com/gaming/azure/reference-architectures/unreal-pixel-streaming-in-azure) and trying out tutorials.
- Read the article About Game Developer Virtual Machine.
