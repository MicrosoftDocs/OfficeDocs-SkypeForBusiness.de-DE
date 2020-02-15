---
title: Installieren der Voraussetzungen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: Hier erfahren Sie mehr über die Server und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018256"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="228b6-104">Installieren der Voraussetzungen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="228b6-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="228b6-105">**Zusammenfassung:** Erfahren Sie mehr über die Server und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren.</span><span class="sxs-lookup"><span data-stu-id="228b6-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="228b6-106">Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.</span><span class="sxs-lookup"><span data-stu-id="228b6-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="228b6-107">Die Installation von Voraussetzungen besteht darin, Windows Server einzurichten, indem die erforderlichen Rollen und Features auf jedem Server in der Topologie installiert werden.</span><span class="sxs-lookup"><span data-stu-id="228b6-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="228b6-108">Die Anforderungen basieren auf der Rolle, die der Server in der Topologie erfüllen wird.</span><span class="sxs-lookup"><span data-stu-id="228b6-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="228b6-109">Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="228b6-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="228b6-110">Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="228b6-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="228b6-111">Installieren von Voraussetzungen ist Schritt 1 von 8.</span><span class="sxs-lookup"><span data-stu-id="228b6-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Overview-Diagramm – installieren Sie die erforderlichen Komponenten.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="228b6-113">Setup von Windows Server</span><span class="sxs-lookup"><span data-stu-id="228b6-113">Setup Windows Server</span></span>

<span data-ttu-id="228b6-114">Skype for Business Server erfordert das Windows Server-Betriebssystem und eine Reihe von Voraussetzungen, bevor es installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="228b6-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="228b6-115">Ausführliche Informationen zur Planung von Voraussetzungen finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="228b6-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="228b6-116">Bei diesem Verfahren wird Windows Server 2012 R2 verwendet.</span><span class="sxs-lookup"><span data-stu-id="228b6-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="228b6-117">Wenn Sie eine andere Version von Windows Server verwenden, ist die Prozedur möglicherweise etwas anders.</span><span class="sxs-lookup"><span data-stu-id="228b6-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="228b6-118">Bevor Sie beginnen, stellen Sie sicher, dass Windows Server auf dem neuesten Stand ist, indem Sie Windows Update verwenden.</span><span class="sxs-lookup"><span data-stu-id="228b6-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="228b6-120">Sehen Sie sich die Video Schritte für **Installationsvoraussetzungen**an:</span><span class="sxs-lookup"><span data-stu-id="228b6-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="228b6-121">Installieren der erforderlichen Rollen und Funktionen für Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="228b6-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="228b6-122">Sie können die erforderlichen Rollen und Funktionen mit dem Server-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="228b6-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="228b6-123">Installieren Sie die unter Server Anforderungen aufgeführten erforderlichen Software Features [für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="228b6-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="228b6-124">Die erforderliche Software muss sich auf dem Server befinden, auf dem Skype for Business Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="228b6-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="228b6-125">In Windows Server 2012 R2 werden standardmäßig nicht alle Quelldateien für die erforderlichen Features installiert.</span><span class="sxs-lookup"><span data-stu-id="228b6-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="228b6-126">Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Medium einfügen und dann **einen alternativen Quell Pfad angeben** , um die erforderlichen Features zu installieren.</span><span class="sxs-lookup"><span data-stu-id="228b6-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="228b6-127">Die Quelldateien befinden sich im sources\sxs-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="228b6-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="228b6-128">Wenn sich beispielsweise das Windows Server 2012 R2-Medium in Laufwerk D befindet, legen Sie den Pfad auf `d:\sources\sxs`fest.</span><span class="sxs-lookup"><span data-stu-id="228b6-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="228b6-129">Es ist wichtig, dass Sie über die neuesten Updates von Windows Update verfügen.</span><span class="sxs-lookup"><span data-stu-id="228b6-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="228b6-130">Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle Voraussetzungen für die erforderlichen Updates manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="228b6-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="228b6-131">Wenn das Dialogfeld angibt, dass die Installation abgeschlossen ist, müssen Sie den Server neu starten, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="228b6-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="228b6-132">Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob die Rollen und Dienste, die installiert wurden, aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="228b6-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="228b6-133">Wenn Sie Skype for Business Server Systemsteuerung auf diesem Server verwenden, müssen Sie auch Silverlight installieren.</span><span class="sxs-lookup"><span data-stu-id="228b6-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="228b6-134">Informationen zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="228b6-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="228b6-135">Die Voraussetzungen für Server, die andere Rollen als Front-End-Server ausführen, wie die Rolle von Director, beständiger Chat oder Edge, haben ihre eigenen Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="228b6-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="228b6-136">Ausführliche Informationen zu den genauen Voraussetzungen, die für die einzelnen Servertypen erforderlich sind, finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="228b6-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

