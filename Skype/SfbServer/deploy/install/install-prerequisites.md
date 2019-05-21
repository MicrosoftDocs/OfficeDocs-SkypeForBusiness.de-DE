---
title: Installieren von Voraussetzungen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: informieren Sie sich über die Server und Serverrollen, die Sie vor der Installation von Skype for Business Server konfigurieren müssen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: 7b2369af5a95d027edff0db291af37c710813465
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306605"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="40bac-104">Installieren von Voraussetzungen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40bac-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="40bac-105">**Zusammenfassung:** Informieren Sie sich über die Server und Serverrollen, die Sie vor der Installation von Skype for Business Server konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="40bac-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="40bac-106">Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.</span><span class="sxs-lookup"><span data-stu-id="40bac-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="40bac-107">Die Installation der erforderlichen Softwarekomponenten besteht in der Einrichtung von Windows Server durch Installation der erforderlichen Rollen und Funktionen auf jedem Server in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="40bac-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="40bac-108">Welche Komponenten erforderlich sind, hängt von der Rolle des jeweiligen Servers in der Topologie ab.</span><span class="sxs-lookup"><span data-stu-id="40bac-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="40bac-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="40bac-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="40bac-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="40bac-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="40bac-111">Die Installation der erforderlichen Softwarekomponenten ist Schritt 1 von 8.</span><span class="sxs-lookup"><span data-stu-id="40bac-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Übersichtsdiagramm – Voraussetzungen für die Installation](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="40bac-113">Einrichten von Windows Server</span><span class="sxs-lookup"><span data-stu-id="40bac-113">Setup Windows Server</span></span>

<span data-ttu-id="40bac-114">Skype for Business Server erfordert das Windows Server-Betriebssystem und eine Reihe von Voraussetzungen, bevor es installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="40bac-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="40bac-115">Einzelheiten zur Planung von Voraussetzungen finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40bac-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="40bac-116">Das nachfolgende Verfahren basiert auf Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="40bac-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="40bac-117">Wenn Sie eine andere Windows Server-Version verwenden, kann die Vorgehensweise leicht abweichen.</span><span class="sxs-lookup"><span data-stu-id="40bac-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="40bac-118">Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="40bac-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="40bac-120">Schauen Sie sich das Video mit den Schritten zum **Imstallieren der erforderlichen Komponenten** an:</span><span class="sxs-lookup"><span data-stu-id="40bac-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="40bac-121">Installieren der erforderlichen Rollen und Funktionen für Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="40bac-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="40bac-122">Sie können die erforderlichen Rollen und Features mit dem Server-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="40bac-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="40bac-123">Installieren Sie die erforderlichen Software Features, die unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md)aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="40bac-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="40bac-124">Die erforderliche Software muss sich auf dem Server befinden, auf dem Skype for Business Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40bac-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="40bac-125">Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien der erforderlichen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="40bac-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="40bac-126">Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Installationsmedium einlegen und **Alternativen Quellpfad angeben** auswählen, um die erforderlichen Funktionen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="40bac-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="40bac-127">Die Quelldateien befinden sich im Verzeichnis „sources\sxs“.</span><span class="sxs-lookup"><span data-stu-id="40bac-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="40bac-128">Wenn sich beispielsweise das Windows Server 2012 R2-Medium auf Laufwerk D befindet, würden Sie den Pfad auf `d:\sources\sxs`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="40bac-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="40bac-129">Es ist wichtig, dass Sie über die neuesten Updates von Windows Update verfügen.</span><span class="sxs-lookup"><span data-stu-id="40bac-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="40bac-130">Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle Voraussetzungen für die erforderlichen Updates manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="40bac-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="40bac-131">Wenn der Abschluss der Installation angezeigt wird, müssen Sie den Server neu starten, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="40bac-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="40bac-132">Führen Sie **Windows Update** erneut aus, um zu prüfen, ob es ein Update für die installierten Rollen und Dienste gibt.</span><span class="sxs-lookup"><span data-stu-id="40bac-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="40bac-133">Wenn Sie die Skype for Business Server-Systemsteuerung auf diesem Server verwenden, müssen Sie auch Silverlight installieren.</span><span class="sxs-lookup"><span data-stu-id="40bac-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="40bac-134">Informationen zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="40bac-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="40bac-135">Für Server, die eine andere Funktion als die eines Front-End-Servers haben, z. B. Director, Persistent Chat oder Edge, sind eigene Softwarekomponenten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40bac-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="40bac-136">Details zu den genauen Voraussetzungen, die für die einzelnen Servertypen erforderlich sind, finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40bac-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

