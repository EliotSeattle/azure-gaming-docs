---
title: Overview of Azure Game Developer Virtual Machine
description: Describes the Azure Game Developer Virtual Machine, sample use cases, and how to use the Azure Game Developer Virtual Machine as a game build server.
author: dciborow
ms.topic: overview
ms.date: 2/1/2022
ms.author: dciborow
ms.prod: azure-gaming
---

# What is the Azure Game Developer Virtual Machine?

The Game Developer Virtual Machine is a customized VM image on the Azure cloud platform, built by game developers for game developers. Supported by GPU intensive Azure VMs, it includes common game development tools, frameworks, remoting protocols, drivers and SDKS, allowing you to get started developing your games in Azure within minutes. It can also be used for scaled-out build servers. In addition to Remote Desktop Protocol, this Game Dev VM includes Teradici CAS (Cloud Access Software), and Parsec remote access technology, which both provide high fidelity and low latency remote access experience.

The Game Developer Virtual Machine is a great choice for developers who are building interactive games that use engines like Unreal or Unity and code with Visual Studio, leveraging Git or Perforce source control solutions. Whether you're working for your next AAA title or an Indie game, spin up an Azure Game Developer VM to enjoy the game development journey in the cloud.

The Game Developer Virtual Machine is available on:

- Windows Server 2019
- Windows 10

## Sample Use Cases

The following illustrates some common use cases for Game Developer Virtual Machine customers.

### Short-term experimentation and evaluation

Game development usually requires high-end computer hardware and a combination of different tools. You can use the Game Developer Virtual Machine to evaluate Azure GPU optimized virtual machines, or learn common game development tools, especially by going through some of our published How-to guides.

### Developing games with game engines

Game engines are a ubiquitous technology driving efficiency in the games industry. They enable developers to create games faster by providing the components and controls that reduce the need to write low-level code. Currently, Unreal and Unity are two dominant engines in the market. The Azure Game Developer Virtual Machine pre-installs either engine based on your need. The Game Developer Virtual Machine also integrates Visual Studio 2019 and VS Plugin, along with various utilities including Game Development Kit, PlayFab SDK, DirectX, and others. You can jump start your game development within minutes, compared to what could be a dozen hours to set up the environment. Furthermore, if you're in an AAA game studio working with multiple developers, the pre-configured Perforce or Git client in Game Developer Virtual Machine can help connect each developer to the code repository for a seamless version control.

Learn more about:

Best practices for Unreal Engine in Azure

Best practices for Unity in Azure

Best practices for Perforce in Azure

Integrate with a GitHub repository

### Using Azure Game Developer Virtual Machine as build servers

You can use this Game Developer Virtual Machine as your game build servers by setting up build machine manually, using virtual machine scale sets, or integrating with Azure Kubernetes Service. This VM has Incredibuild Visual Studio Plugin pre-installed, which connects other build servers to dramatically reduce the build time by using parallel computing. Storage and network configuration will also be taken into consideration to further accelerate the build speed.

Learn more about:

Using the Game Developer Virtual Machine as a build server

Integrate with Incredibuild

## What's included on the Game Developer Virtual Machine

See a full list of tools on DSVMs here.

## Next steps

Create a Game Developer Virtual Machine with Unreal Engine

Create a Game Developer Virtual Machine with Unity
