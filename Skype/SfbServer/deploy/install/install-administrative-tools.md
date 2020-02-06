---
title: Installieren von Verwaltungstools in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Verwaltungstools installieren, die für die Installation von Skype for Business Server erforderlich sind. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790173"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="6c9ae-104">Installieren von Verwaltungstools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6c9ae-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="6c9ae-105">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Verwaltungstools installieren, die für die Installation von Skype for Business Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="6c9ae-106">Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Center unter: herunter.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="6c9ae-107">Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="6c9ae-108">Die Verwaltungstools müssen auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation installiert sein, auf der eine Windows-Betriebssystemversion ausgeführt wird, die für Skype for Business Server unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="6c9ae-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="6c9ae-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="6c9ae-111">Die Installation der Verwaltungstools wird in Schritt 3 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Übersichtsdiagramm](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="6c9ae-113">Installieren von Skype for Business Server-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="6c9ae-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="6c9ae-114">Das Installationsmedium für Skype for Business Server bietet eine flexible Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="6c9ae-115">Beim ersten Ausführen von Setup. exe sind die einzigen installierten Tools der Skype for Business Server-Bereitstellungs-Assistent und die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="6c9ae-116">Durch die Verwendung dieser beiden Tools, so genannten Core-Komponenten, können Sie den Installationsvorgang fortsetzen, Sie bieten jedoch keine primäre Funktionalität für die gesamte Skype for Business Server-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="6c9ae-117">Der Bereitstellungs-Assistent wird nach Installation der Hauptkomponenten automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="6c9ae-118">Der Abschnitt des Bereitstellungs-Assistenten mit dem Titel **install Administration Tools** installiert den Skype for Business Server Topology Builder und die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c9ae-119">Jede Skype for Business Server-Umgebung muss mindestens einen Server besitzen, auf dem die Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="6c9ae-120">Schauen Sie sich das Video mit den Schritten zum **Installieren von Verwaltungstools** an:</span><span class="sxs-lookup"><span data-stu-id="6c9ae-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="6c9ae-121">Installieren von Skype for Business Server-Verwaltungstools aus dem Bereitstellungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="6c9ae-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="6c9ae-122">Legen Sie das Skype for Business Server-Installationsmedium ein.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="6c9ae-123">Wenn das Setup nicht automatisch startet, doppelklicken Sie auf **Setup**.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="6c9ae-p106">Das Installationsmedium erfordert zur Ausführung Microsoft Visual C++. Es wird ein Dialogfeld angezeigt, in dem gefragt wird, ob Sie es installieren möchten. Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="6c9ae-127">Durch die Verwendung von Smart Setup, einer neuen Funktion in Skype for Business Server, können Sie eine Verbindung mit dem Internet herstellen, um während des Installationsvorgangs nach Updates zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="6c9ae-128">Dies ist benutzerfreundlicher, da sichergestellt wird, dass Sie bei der Installation die aktuellen Updates zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="6c9ae-129">Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="6c9ae-130">Lesen Sie die Lizenzbedingungen sorgfältig durch und klicken Sie auf **Ich stimme den Lizenzbedingungen zu**, wenn Sie diesen zustimmen. Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="6c9ae-131">Die Skype for Business Server-Core-Komponenten werden auf dem Server installiert.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="6c9ae-132">Die Hauptkomponenten werden in der Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Hauptkomponenten auf dem Apps-Bildschirm.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="6c9ae-134">**Skype for Business Server-Bereitstellungs-Assistent** Ein Bereitstellungsprogramm, das eine Startrampe zum Installieren der verschiedenen Komponenten von Skype for Business Server bietet.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="6c9ae-135">**Skype for Business Server-Verwaltungsshell** Ein vorkonfiguriertes PowerShell-Programm, das die Verwaltung von Skype for Business Server ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="6c9ae-136">Nachdem die Installation der Kernkomponenten abgeschlossen ist, wird der Skype for Business Server-Bereitstellungs-Assistent automatisch gestartet, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server-Bereitstellungsassistent](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="6c9ae-138">Zusätzlich zu den Kernkomponenten müssen Sie auch den Skype for Business Server Topology Builder und die Skype for Business Server-Systemsteuerung auf mindestens einem Server in der Umgebung installieren.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="6c9ae-139">Klicken Sie im Bereitstellungs-Assistenten auf **Verwaltungstools installieren**.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="6c9ae-140">Klicken Sie auf **Weiter**, um den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="6c9ae-p109">Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig stellen**. Die Verwaltungstools wurden nun dem Server hinzugefügt (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="6c9ae-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server-Verwaltungs Tools](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="6c9ae-144">**Skype for Business Server-Topologie-Generator** Ein Programm, das zum Erstellen, bereitstellen und Verwalten von Topologien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="6c9ae-145">**Skype for Business Server-System** Steuerung Ein Programm, das zum Verwalten der Installation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

