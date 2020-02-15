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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die für eine Installation von Skype for Business Server erforderlichen Verwaltungstools installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018266"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="5ccab-104">Installieren von Verwaltungstools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5ccab-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="5ccab-105">**Zusammenfassung:** Hier erfahren Sie, wie Sie die für eine Installation von Skype for Business Server erforderlichen Verwaltungstools installieren.</span><span class="sxs-lookup"><span data-stu-id="5ccab-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="5ccab-106">Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)unter: herunter.</span><span class="sxs-lookup"><span data-stu-id="5ccab-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="5ccab-107">Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="5ccab-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="5ccab-108">Die Verwaltungstools müssen auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation mit einer Windows-Betriebssystemversion installiert werden, die für Skype for Business Server unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5ccab-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="5ccab-109">Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="5ccab-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="5ccab-110">Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5ccab-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="5ccab-111">Das Installieren der Verwaltungstools ist der Schritt 3 von 8.</span><span class="sxs-lookup"><span data-stu-id="5ccab-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Übersicht Diagramm](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="5ccab-113">Installieren von Skype for Business Server Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="5ccab-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="5ccab-114">Die Installationsmedien für Skype for Business Server bieten eine flexible Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="5ccab-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="5ccab-115">Bei der ersten Ausführung von "Setup. exe" werden nur die Skype for Business Server-Bereitstellungs-Assistenten und die Skype for Business Server-Verwaltungsshell installiert.</span><span class="sxs-lookup"><span data-stu-id="5ccab-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5ccab-116">Durch die Verwendung dieser beiden Tools, die als Kernkomponenten bezeichnet werden, können Sie den Installationsvorgang fortsetzen, Sie bieten jedoch keine primäre Funktionalität für die gesamte Skype for Business Server Umgebung.</span><span class="sxs-lookup"><span data-stu-id="5ccab-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="5ccab-117">Der Bereitstellungs-Assistent wird automatisch gestartet, nachdem Sie die Hauptkomponenten installiert haben.</span><span class="sxs-lookup"><span data-stu-id="5ccab-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="5ccab-118">Im Abschnitt **install Administration Tools** des Bereitstellungs-Assistenten werden Skype for Business Server Topologie-Generator und Skype for Business Server Systemsteuerung installiert.</span><span class="sxs-lookup"><span data-stu-id="5ccab-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5ccab-119">In jeder Skype for Business Server Umgebung muss mindestens ein Server vorhanden sein, auf dem die Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="5ccab-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="5ccab-120">Sehen Sie sich die Video Schritte für die **Installation von Verwaltungstools**an:</span><span class="sxs-lookup"><span data-stu-id="5ccab-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="5ccab-121">Installieren von Skype for Business Server Verwaltungstools im Bereitstellungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="5ccab-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="5ccab-122">Legen Sie das Skype for Business Server Installationsmedium ein.</span><span class="sxs-lookup"><span data-stu-id="5ccab-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="5ccab-123">Wenn das Setup nicht automatisch gestartet wird, doppelklicken Sie auf **Setup**.</span><span class="sxs-lookup"><span data-stu-id="5ccab-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="5ccab-124">Für die Installationsmedien muss Microsoft Visual C++ ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5ccab-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="5ccab-125">Ein Dialogfeld wird eingeblendet, in dem Sie gefragt werden, ob Sie es installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5ccab-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="5ccab-126">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="5ccab-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="5ccab-127">Mithilfe von Smart Setup, einem neuen Feature in Skype for Business Server, können Sie eine Verbindung mit dem Internet herstellen, um während des Installationsvorgangs nach Updates zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5ccab-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="5ccab-128">Dies bietet eine bessere Erfahrung, indem Sie sicherstellen, dass Sie über die neuesten Updates für das Produkt bei der Installation verfügen.</span><span class="sxs-lookup"><span data-stu-id="5ccab-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="5ccab-129">Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="5ccab-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="5ccab-130">Überprüfen Sie den Lizenzvertrag sorgfältig, und wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags**zu, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ccab-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="5ccab-131">Die Skype for Business Server Kernkomponenten werden auf dem Server installiert.</span><span class="sxs-lookup"><span data-stu-id="5ccab-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="5ccab-132">Die Kernkomponenten bestehen aus den folgenden, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5ccab-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Hauptkomponenten auf dem Bildschirm "Apps".](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="5ccab-134">**Skype for Business Server-Bereitstellungs-Assistent** Ein Bereitstellungsprogramm, das eine Startrampe für die Installation der verschiedenen Komponenten von Skype for Business Server bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5ccab-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="5ccab-135">**Skype for Business Server Management-Shell** Ein vorkonfiguriertes PowerShell-Programm, das die Verwaltung von Skype for Business Server ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5ccab-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="5ccab-136">Nachdem die Installation der Kernkomponenten abgeschlossen ist, wird der Skype for Business Server-Bereitstellungs-Assistent automatisch gestartet, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5ccab-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server-Bereitstellungs-Assistent](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="5ccab-138">Zusätzlich zu den Hauptkomponenten müssen Sie auch Skype for Business Server Topologie-Generator und Skype for Business Server Systemsteuerung auf mindestens einem Server in der Umgebung installieren.</span><span class="sxs-lookup"><span data-stu-id="5ccab-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="5ccab-139">Klicken Sie im Bereitstellungs-Assistenten auf **Verwaltungs Tools installieren** .</span><span class="sxs-lookup"><span data-stu-id="5ccab-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="5ccab-140">Klicken Sie auf **Weiter**, um die Installation zu starten.</span><span class="sxs-lookup"><span data-stu-id="5ccab-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="5ccab-141">Klicken Sie nach Abschluss der Installation auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="5ccab-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="5ccab-142">Die Verwaltungstools werden nun dem Server hinzugefügt, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5ccab-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server Verwaltungs Tools](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="5ccab-144">**Skype for Business Server Topologie-Generator** Ein Programm, das zum Erstellen, bereitstellen und Verwalten von Topologien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ccab-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="5ccab-145">**Skype for Business Server-System** Steuerung Ein Programm, mit dem die Installation verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="5ccab-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

