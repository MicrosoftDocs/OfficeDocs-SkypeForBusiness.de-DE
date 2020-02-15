---
title: Voraussetzungen und Setup für das Skype for Business Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. Vorgehensweise zum Installieren oder Einrichten des Stress-und Leistungstools.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005980"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="fd29a-104">Voraussetzungen und Setup für das Skype for Business Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="fd29a-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="fd29a-105">Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="fd29a-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="fd29a-106">Vorgehensweise zum Installieren oder Einrichten des Stress-und Leistungstools.</span><span class="sxs-lookup"><span data-stu-id="fd29a-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="fd29a-107">Wir haben die folgenden Abschnitte der Hardware-, Software-und System Konfigurationsanforderungen, die Sie vor der Ausführung des Stress-und Leistungstools beachten müssen:</span><span class="sxs-lookup"><span data-stu-id="fd29a-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="fd29a-108">Client Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="fd29a-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="fd29a-109">Client Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="fd29a-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="fd29a-110">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="fd29a-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="fd29a-111">Darüber hinaus haben wir auch einen Abschnitt unten für [die Installation des Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="fd29a-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="fd29a-112">Client Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="fd29a-112">Client hardware requirements</span></span>
<span data-ttu-id="fd29a-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="fd29a-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="fd29a-114">Wenn Sie das Belastungs-und Leistungs Tool für Ihre Skype for Business Server 2015-Bereitstellung verwenden, müssen Sie mindestens diese Hardwareanforderungen erfüllen, die für alle 4500-Benutzer in Ihrem Test erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="fd29a-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="fd29a-115">1 Gigabit-Netzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="fd29a-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="fd29a-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="fd29a-116">8 GB RAM</span></span>
    
- <span data-ttu-id="fd29a-117">2 Dual-Core-CPUs</span><span class="sxs-lookup"><span data-stu-id="fd29a-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="fd29a-118">Client Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="fd29a-118">Client software requirements</span></span>
<span data-ttu-id="fd29a-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="fd29a-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="fd29a-120">Die unterstützten Betriebssysteme für das Tool Stress and Performance sind:</span><span class="sxs-lookup"><span data-stu-id="fd29a-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="fd29a-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fd29a-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="fd29a-122">Windows Server 2008 (64-Bit)</span><span class="sxs-lookup"><span data-stu-id="fd29a-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="fd29a-123">Darüber hinaus müssen Computer die folgenden Softwareanforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="fd29a-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="fd29a-124">Sie benötigen das Microsoft .NET 4,5 Framework installiert.</span><span class="sxs-lookup"><span data-stu-id="fd29a-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="fd29a-125">Laden Sie das .NET 4,5 Framework hier herunter.</span><span class="sxs-lookup"><span data-stu-id="fd29a-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="fd29a-126">Sie benötigen das Feature "Desktop Experience" in Windows aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fd29a-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="fd29a-127">Sie müssen Microsoft Visual C++ 2013 (x64) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="fd29a-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="fd29a-128">Visual C++ 2013 hier herunterladen</span><span class="sxs-lookup"><span data-stu-id="fd29a-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="fd29a-129">Sie benötigen Skype for Business Server 2015 erfolgreich bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fd29a-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="fd29a-130">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="fd29a-130">Configuration requirements</span></span>
<span data-ttu-id="fd29a-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="fd29a-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="fd29a-132">Sie benötigen diese zusätzlichen Konfigurationen, um das Stress-und Leistungs Tool erfolgreich auszuführen:</span><span class="sxs-lookup"><span data-stu-id="fd29a-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="fd29a-133">Sie müssen sich beim Server als Mitglied der Domäne oder der Gruppe des lokalen Administrators anmelden.</span><span class="sxs-lookup"><span data-stu-id="fd29a-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="fd29a-134">Sie können das Skype for Business Server 2015-Benutzer Erstellungstool (UserProvisioningTool. exe) nicht auf einem Front-End-Server oder Standard Edition-Server installieren, in dem sich die Benutzerkonten befinden.</span><span class="sxs-lookup"><span data-stu-id="fd29a-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="fd29a-135">Wenn das Benutzer Erstellungstool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.</span><span class="sxs-lookup"><span data-stu-id="fd29a-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="fd29a-136">Die Größe der Auslagerungsdatei sollte System verwaltet sein oder muss auf andere Weise mindestens 1,5 mal so viel RAM im Computersystem sein.</span><span class="sxs-lookup"><span data-stu-id="fd29a-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="fd29a-137">Installieren des Skype for Business Server 2015-Tools für Stress und Leistung</span><span class="sxs-lookup"><span data-stu-id="fd29a-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="fd29a-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="fd29a-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="fd29a-139">Die Installation kann nicht einfacher sein.</span><span class="sxs-lookup"><span data-stu-id="fd29a-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="fd29a-140">Sie müssen die Windows Installer-Datei **CapacityPlanningTool. msi**auf jedem Clientcomputer ausführen, den Sie zum Simulieren des Benutzerdatenverkehrs verwenden werden, und auf einer Front-End-Server in jedem Pool, in dem Sie Benutzer und Kontakte erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd29a-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="fd29a-141">Um die MSI-Datei sowie die in den anderen Artikeln erwähnten Beispielskripts herunterzuladen, wechseln Sie zum Download Center-Link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="fd29a-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

