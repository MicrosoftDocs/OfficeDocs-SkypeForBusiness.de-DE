---
title: Voraussetzungen und Setup für Skype for Business Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Anforderungen oder Voraussetzungen für Skype for Business Server 2015 Stress and Performance Tool. Installieren oder Setup des Stress and Performance Tool.
ms.openlocfilehash: fbc04202ea9b0719be9b8221d43171d58fe772b7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995291"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="a07a4-104">Voraussetzungen und Setup für Skype for Business Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a07a4-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="a07a4-105">Anforderungen oder Voraussetzungen für Skype for Business Server 2015 Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="a07a4-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="a07a4-106">Installieren oder Setup des Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="a07a4-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="a07a4-107">Die folgenden Abschnitte enthalten Anforderungen für Hardware, Software und Systemkonfiguration, die Sie beachten müssen, bevor Sie Stress and Performance Tool ausführen:</span><span class="sxs-lookup"><span data-stu-id="a07a4-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="a07a4-108">Clienthardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="a07a4-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="a07a4-109">Clientsoftwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="a07a4-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="a07a4-110">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="a07a4-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="a07a4-111">Außerdem gibt es einen Abschnitt zum [Installieren von Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing).</span><span class="sxs-lookup"><span data-stu-id="a07a4-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="a07a4-112">Clienthardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="a07a4-112">Client hardware requirements</span></span>
<span data-ttu-id="a07a4-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="a07a4-113"></span></span>

<span data-ttu-id="a07a4-114">Wenn Sie Stress and Performance Tool für Ihre Skype for Business Server 2015-Bereitstellung ausführen, müssen mindestens die folgenden Hardwareanforderungen für jeweils 4.500 Benutzer in Ihrem Test erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="a07a4-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="a07a4-115">1 Gigabitnetzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="a07a4-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="a07a4-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="a07a4-116">8 GB RAM</span></span>
    
- <span data-ttu-id="a07a4-117">2 Doppelkern-CPUs</span><span class="sxs-lookup"><span data-stu-id="a07a4-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="a07a4-118">Clientsoftwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="a07a4-118">Client software requirements</span></span>
<span data-ttu-id="a07a4-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="a07a4-119"></span></span>

<span data-ttu-id="a07a4-120">Die folgenden Betriebssysteme werden für Stress and Performance Tool unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a07a4-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="a07a4-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a07a4-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="a07a4-122">Windows Server 2008 (64-Bit)</span><span class="sxs-lookup"><span data-stu-id="a07a4-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="a07a4-123">Darüber hinaus müssen die Computer die folgenden Softwareanforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a07a4-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="a07a4-124">Microsoft .NET 4.5 Framework muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="a07a4-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="a07a4-125">Laden Sie die .net 4.5 hier Framework.</span><span class="sxs-lookup"><span data-stu-id="a07a4-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- <span data-ttu-id="a07a4-126">In Windows muss die Funktion Desktopdarstellung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="a07a4-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="a07a4-127">Microsoft Visual C++ 2013 (x64) muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="a07a4-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="a07a4-128">Visual C++-2013 hier herunterladen</span><span class="sxs-lookup"><span data-stu-id="a07a4-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- <span data-ttu-id="a07a4-129">Skype for Business Server 2015 muss erfolgreich bereitgestellt sein.</span><span class="sxs-lookup"><span data-stu-id="a07a4-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="a07a4-130">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="a07a4-130">Configuration requirements</span></span>
<span data-ttu-id="a07a4-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="a07a4-131"></span></span>

<span data-ttu-id="a07a4-132">Außerdem müssen Sie diese Konfigurationen vornehmen, um Stress and Performance Tool erfolgreich auszuführen:</span><span class="sxs-lookup"><span data-stu-id="a07a4-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="a07a4-133">Sie müssen sich als Mitglied der Domänenadministratorgruppe oder der lokalen Administratorgruppe beim Server anmelden.</span><span class="sxs-lookup"><span data-stu-id="a07a4-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="a07a4-134">Sie können das Skype for Business Server 2015-Benutzererstellungstool („UserProvisioningTool.exe“) auf einem beliebigen Front-End-Server oder Standard Edition-Server ausführen, auf dem sich die Benutzerkonten befinden werden.</span><span class="sxs-lookup"><span data-stu-id="a07a4-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="a07a4-135">Wenn das Benutzererstellungstool mehrmals ausgeführt wird, benötigt jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, eine eindeutige Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="a07a4-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="a07a4-136">Die Größe der Auslagerungsdatei sollte vom System verwaltet werden oder andernfalls mindestens das 1,5-Fache der RAM-Größe im Computersystem betragen.</span><span class="sxs-lookup"><span data-stu-id="a07a4-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="a07a4-137">Installieren von Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a07a4-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="a07a4-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="a07a4-138"></span></span>

<span data-ttu-id="a07a4-139">Die Installation ist ganz einfach.</span><span class="sxs-lookup"><span data-stu-id="a07a4-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="a07a4-140">Sie müssen auf jedem Computer, auf dem Sie Benutzerdatenverkehr simulieren möchten, sowie auf einem Front-End-Server in jedem Pool, in dem Sie Benutzer und Kontakte erstellen werden, die Windows Installer-Datei **CapacityPlanningTool.msi** ausführen.</span><span class="sxs-lookup"><span data-stu-id="a07a4-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="a07a4-141">Laden Sie die MSI-Datei zusammen mit der Beispielskripts in unsere anderen Artikeln erwähnten finden Sie auf den Link Download Center: [Skype für Business Server 2015, Stress and Performance-Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="a07a4-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

