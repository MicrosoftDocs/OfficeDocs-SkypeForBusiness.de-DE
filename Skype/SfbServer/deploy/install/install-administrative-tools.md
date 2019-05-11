---
title: Installieren der Verwaltungstools in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Zusammenfassung: Informationen Sie zum Installieren der erforderlichen für eine Installation von Skype für Business Server administrative Tools. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: cb5e1766ca4e0b7d6ad03db2004835e1a51d52cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891831"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="43254-104">Installieren der Verwaltungstools in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="43254-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="43254-105">**Zusammenfassung:** Informationen Sie zum Installieren der erforderlichen für eine Installation von Skype für Business Server administrative Tools.</span><span class="sxs-lookup"><span data-stu-id="43254-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="43254-106">Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="43254-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="43254-107">Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="43254-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="43254-108">Auf mindestens einem Server in der Topologie oder einem 64-Bit-Verwaltungscomputer auf dem eine Windows-Betriebssystem-Version, die für Skype für Business Server unterstützt wird, müssen die Verwaltungstools installiert werden.</span><span class="sxs-lookup"><span data-stu-id="43254-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="43254-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="43254-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="43254-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43254-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="43254-111">Die Installation der Verwaltungstools wird in Schritt 3 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="43254-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Übersichtsdiagramm](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="43254-113">Skype für Business Server-Verwaltungstools installieren</span><span class="sxs-lookup"><span data-stu-id="43254-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="43254-114">Das Installationsmedium für Skype für Business Server bietet flexible.</span><span class="sxs-lookup"><span data-stu-id="43254-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="43254-115">Beim Ausführen von Setup.exe sind die einzigen Tools installiert die Skype für Business Server-Bereitstellungs-Assistenten und den Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="43254-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="43254-116">Mithilfe dieser zwei Tools, bezeichnet als Hauptkomponenten, können Sie den Installationsvorgang fortsetzen, aber sie bieten keine primäre Funktionalität für die allgemeine Skype für Business Server-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="43254-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="43254-117">Der Bereitstellungs-Assistent wird nach Installation der Hauptkomponenten automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="43254-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="43254-118">Im Abschnitt des Bereitstellungs-Assistenten mit dem Titel **Verwaltungstools installieren** installiert Skype für Business Server-Topologie-Generator und Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="43254-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="43254-119">Jeder Skype für Business Server-Umgebung benötigen Sie mindestens einen Server mit die Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="43254-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="43254-120">Schauen Sie sich das Video mit den Schritten zum **Installieren von Verwaltungstools** an:</span><span class="sxs-lookup"><span data-stu-id="43254-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="43254-121">Installieren Sie Skype für Business Server-Verwaltungstools aus den Bereitstellungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="43254-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="43254-122">Legen Sie die Skype für Business Server-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="43254-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="43254-123">Wenn das Setup nicht automatisch startet, doppelklicken Sie auf **Setup**.</span><span class="sxs-lookup"><span data-stu-id="43254-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="43254-p106">Das Installationsmedium erfordert zur Ausführung Microsoft Visual C++. Es wird ein Dialogfeld angezeigt, in dem gefragt wird, ob Sie es installieren möchten. Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="43254-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="43254-127">Mithilfe der Smart-Setup ein neues Feature in Skype für Business Server können Sie mit dem Internet während der Installation nach Updates suchen verbinden.</span><span class="sxs-lookup"><span data-stu-id="43254-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="43254-128">Dies ist benutzerfreundlicher, da sichergestellt wird, dass Sie bei der Installation die aktuellen Updates zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="43254-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="43254-129">Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="43254-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="43254-130">Lesen Sie die Lizenzbedingungen sorgfältig durch und klicken Sie auf **Ich stimme den Lizenzbedingungen zu**, wenn Sie diesen zustimmen. Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="43254-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="43254-131">Die Skype für Business Server Core-Komponenten wird auf dem Server installiert.</span><span class="sxs-lookup"><span data-stu-id="43254-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="43254-132">Die Hauptkomponenten werden in der Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="43254-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Hauptkomponenten auf dem Apps-Bildschirm.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="43254-134">**Skype für Business Server-Bereitstellungs-Assistenten** Eine Bereitstellung-Programm, das ein Launch Pad enthält, für die verschiedenen Komponenten von Skype für Business Server installieren.</span><span class="sxs-lookup"><span data-stu-id="43254-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="43254-135">**Skype für Business Server-Verwaltungsshell** Eine vorkonfigurierte PowerShell-Programm, das für die Verwaltung von Skype für Business Server ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="43254-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="43254-136">Nach Abschluss die Installation der Kernkomponenten wird die Skype für Business Server Installations-Assistent automatisch gestartet, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="43254-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server-Bereitstellungsassistent](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="43254-138">Zusätzlich zu den Hauptkomponenten müssen Sie auch Skype für Business Server-Topologie-Generator und Skype Business Server-Systemsteuerung auf mindestens einem Server in der Umgebung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="43254-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="43254-139">Klicken Sie im Bereitstellungs-Assistenten auf **Verwaltungstools installieren**.</span><span class="sxs-lookup"><span data-stu-id="43254-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="43254-140">Klicken Sie auf **Weiter**, um den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="43254-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="43254-p109">Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig stellen**. Die Verwaltungstools wurden nun dem Server hinzugefügt (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="43254-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype für Business Server-Verwaltungstools](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="43254-144">**Skype für Business Server-Topologie-Generator** Ein Programm, das zum Erstellen, bereitstellen und Verwalten von Topologien verwendet.</span><span class="sxs-lookup"><span data-stu-id="43254-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="43254-145">**Skype für Business Server-Systemsteuerung** Ein Programm verwendet, um die Installation zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="43254-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

