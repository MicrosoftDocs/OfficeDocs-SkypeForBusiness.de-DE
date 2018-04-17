---
title: Verwaltungstools in Skype for Business Server 2015 installieren
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Summary: Learn how to install the administrative tools required for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: c0d6b4a2ad41fbca4c89e6095a34eabf08e191ee
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a><span data-ttu-id="0d9b8-104">Verwaltungstools in Skype for Business Server 2015 installieren</span><span class="sxs-lookup"><span data-stu-id="0d9b8-104">Install administrative tools in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0d9b8-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="0d9b8-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="0d9b8-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="0d9b8-107">Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="0d9b8-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="0d9b8-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="0d9b8-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="0d9b8-111">Die Installation der Verwaltungstools wird in Schritt 3 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Übersichtsdiagramm](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a><span data-ttu-id="0d9b8-113">Install Skype for Business Server 2015 administrative tools</span><span class="sxs-lookup"><span data-stu-id="0d9b8-113">Install Skype for Business Server 2015 administrative tools</span></span>

<span data-ttu-id="0d9b8-114">The installation media for Skype for Business Server 2015 provides a flexible experience.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-114">The installation media for Skype for Business Server 2015 provides a flexible experience.</span></span> <span data-ttu-id="0d9b8-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0d9b8-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="0d9b8-117">Der Bereitstellungs-Assistent wird nach Installation der Hauptkomponenten automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="0d9b8-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0d9b8-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="0d9b8-120">Schauen Sie sich das Video mit den Schritten zum **Installieren von Verwaltungstools** an:</span><span class="sxs-lookup"><span data-stu-id="0d9b8-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="0d9b8-121">Install Skype for Business Server 2015 administrative tools from the Deployment Wizard</span><span class="sxs-lookup"><span data-stu-id="0d9b8-121">Install Skype for Business Server 2015 administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="0d9b8-122">Insert the Skype for Business Server 2015 installation media.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-122">Insert the Skype for Business Server 2015 installation media.</span></span> <span data-ttu-id="0d9b8-123">Wenn das Setup nicht automatisch startet, doppelklicken Sie auf **Setup**.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="0d9b8-p106">Das Installationsmedium erfordert zur Ausführung Microsoft Visual C++. Es wird ein Dialogfeld angezeigt, in dem gefragt wird, ob Sie es installieren möchten. Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="0d9b8-127">By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-127">By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="0d9b8-128">Dies ist benutzerfreundlicher, da sichergestellt wird, dass Sie bei der Installation die aktuellen Updates zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="0d9b8-129">Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="0d9b8-130">Lesen Sie die Lizenzbedingungen sorgfältig durch und klicken Sie auf **Ich stimme den Lizenzbedingungen zu**, wenn Sie diesen zustimmen. Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="0d9b8-131">The Skype for Business Server 2015 Core Components will be installed on the server.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-131">The Skype for Business Server 2015 Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="0d9b8-132">Die Hauptkomponenten werden in der Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Hauptkomponenten auf dem Apps-Bildschirm.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - <span data-ttu-id="0d9b8-134">**Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-134">**Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.</span></span>
    
  - <span data-ttu-id="0d9b8-135">**Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-135">**Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.</span></span>
    
    <span data-ttu-id="0d9b8-136">Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-136">Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
    ![Skype for Business Server 2015 – Bereitstellungs-Assistent](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="0d9b8-138">In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-138">In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="0d9b8-139">Klicken Sie im Bereitstellungs-Assistenten auf **Verwaltungstools installieren**.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="0d9b8-140">Klicken Sie auf **Weiter**, um den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="0d9b8-p109">Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig stellen**. Die Verwaltungstools wurden nun dem Server hinzugefügt (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="0d9b8-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 2015-Verwaltungstools](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="0d9b8-144">**Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-144">**Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="0d9b8-145">**Skype for Business Server 2015 Control Panel** A program used to administer the installation.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-145">**Skype for Business Server 2015 Control Panel** A program used to administer the installation.</span></span>
    

