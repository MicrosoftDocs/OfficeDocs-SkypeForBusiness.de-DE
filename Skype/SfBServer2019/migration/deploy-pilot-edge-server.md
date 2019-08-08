---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihres Skype for Business Server 2019 Edge-Servers beachten sollten. Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 sind mit Skype for Business Server 2015 sehr ähnlich. In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten. Detaillierte Anweisungen finden Sie unter Bereitstellen des Zugriffs auf externe Benutzer in Skype for Business Server 2019 in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird, sowie Konfigurationsinformationen für den Zugriff durch externe Benutzer.
ms.openlocfilehash: b416ba38646d05f3d10a7d2643c01924fe57020a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238388"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="9ab52-106">Bereitstellen eines Pilot-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="9ab52-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="9ab52-107">In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie berücksichtigen sollten, bevor Sie Ihren Skype for Business Server 2019 Edge-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9ab52-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="9ab52-108">Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 sind mit Skype for Business Server 2015 sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="9ab52-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="9ab52-109">In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="9ab52-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="9ab52-110">Wenn Sie im Assistenten zum **Definieren eines neuen Edge-Pools** navigieren, überprüfen Sie die wichtigsten Konfigurationseinstellungen, die in den folgenden Schritten gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9ab52-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="9ab52-111">Beachten Sie, dass nur wenige Seiten des Assistenten zum **Definieren eines neuen Edge-Pools** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9ab52-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="9ab52-112">So definieren Sie einen Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="9ab52-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="9ab52-113">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="9ab52-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="9ab52-114">Navigieren Sie zum Skype for Business Server 2019-Knoten.</span><span class="sxs-lookup"><span data-stu-id="9ab52-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="9ab52-115">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie auf **neuer Edge-Pool**.</span><span class="sxs-lookup"><span data-stu-id="9ab52-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Dialogfeld ' neuen Edge-Pool definieren '](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="9ab52-117">Ein Edge-Pool kann ein Pool mit **mehreren Computern** oder ein **einzelner Computerpool**sein.</span><span class="sxs-lookup"><span data-stu-id="9ab52-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Definieren des Dialogfelds "FQDN des Edge-Pools"](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="9ab52-119">Aktivieren Sie auf der Seite **"Features auswählen** " die Föderation oder den XMPP-Verbund nicht.</span><span class="sxs-lookup"><span data-stu-id="9ab52-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="9ab52-120">Föderation und XMPP-Föderation sind beide derzeit über den Legacy-Edgeserver geroutet.</span><span class="sxs-lookup"><span data-stu-id="9ab52-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="9ab52-121">Diese Features werden in einer späteren Migrationsphase konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9ab52-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="9ab52-122">Führen Sie die folgenden Assistentenseiten aus: **externe FQDNs**, **definieren Sie die interne IP-Adresse**, und definieren Sie **die externe IP-Adresse**.</span><span class="sxs-lookup"><span data-stu-id="9ab52-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="9ab52-123">Wählen Sie auf der Seite **Nächster Hop-Server definieren** den Director für den nächsten Hop des Legacy-Edge-Pools aus.</span><span class="sxs-lookup"><span data-stu-id="9ab52-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Dialogfeld ' nächster Hop definieren '](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="9ab52-125">Verbinden Sie auf der Seite **Front-End-oder Mediations Pools zuordnen** keinen Pool mit diesem Edge-Pool zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="9ab52-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="9ab52-126">Der externe Mediendatenverkehr wird derzeit über den Legacy-Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="9ab52-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="9ab52-127">Diese Einstellung wird in einer späteren Migrationsphase konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9ab52-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Dialogfeld ' Front-End-Pools zuordnen '](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="9ab52-129">Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="9ab52-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="9ab52-130">Führen Sie die Schritte in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="9ab52-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="9ab52-131">Es ist sehr wichtig, dass Sie die Richtlinien in den Themen in der Bereitstellungsdokumentation befolgen.</span><span class="sxs-lookup"><span data-stu-id="9ab52-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="9ab52-132">Dieser Abschnitt enthält lediglich einige Anleitungen zu Konfigurationseinstellungen beim Installieren dieser Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="9ab52-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="9ab52-133">Sie sollten jetzt einen Legacy-Edgeserver parallel zu einer Skype for Business Server 2019 Edge Server-Bereitstellung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9ab52-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="9ab52-134">Überprüfen Sie, ob beide Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie können jede Bereitstellung verwalten, bevor Sie in die nächste Phase wechseln.</span><span class="sxs-lookup"><span data-stu-id="9ab52-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

