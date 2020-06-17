---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Thema werden Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer Skype for Business Server 2019 Edgeserver beachten sollten. Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 ähneln Skype for Business Server 2015. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Anweisungen finden Sie unter Deploying External User Access in Skype for Business Server 2019 in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird und der auch Konfigurationsinformationen für den Zugriff durch externe Benutzer enthält.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752867"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="255ea-106">Bereitstellen eines Pilot-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="255ea-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="255ea-107">In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer Skype for Business Server 2019 Edgeserver beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="255ea-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="255ea-108">Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 ähneln Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="255ea-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="255ea-109">In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="255ea-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="255ea-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="255ea-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="255ea-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="255ea-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="255ea-112">So definieren Sie einen Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="255ea-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="255ea-113">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="255ea-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="255ea-114">Navigieren Sie zum Knoten Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="255ea-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="255ea-115">Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.</span><span class="sxs-lookup"><span data-stu-id="255ea-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Definieren des Dialogfelds "neuer Edge-Pool"](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="255ea-117">Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer**.</span><span class="sxs-lookup"><span data-stu-id="255ea-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Definieren des Dialogfelds für den FQDN des Edge-Pools](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="255ea-119">Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund.</span><span class="sxs-lookup"><span data-stu-id="255ea-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="255ea-120">Der Partnerverbund und der XMPP-Verbund werden derzeit über die Legacy Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="255ea-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="255ea-121">Diese Funktionen werden in einer späteren Phase der Migration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="255ea-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="255ea-122">Beenden Sie die folgenden Assistentenseiten: **externe FQDNs**, **definieren Sie die interne IP-Adresse**, und **definieren Sie die externe IP-Adresse**.</span><span class="sxs-lookup"><span data-stu-id="255ea-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="255ea-123">Wählen Sie auf der Seite **nächsten Hop-Server definieren** den Director für den nächsten Hop der Legacy Edgepool aus.</span><span class="sxs-lookup"><span data-stu-id="255ea-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Definieren des nächsten Hops (Dialogfeld)](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="255ea-125">Verknüpfen Sie auf der Seite **Front-End-oder Vermittlungs Pools zuordnen** keinen Pool mit diesem Edgepool zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="255ea-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="255ea-126">Der externe Mediendatenverkehr wird derzeit über die Legacy Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="255ea-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="255ea-127">Diese Einstellung wird in einer späteren Phase der Migration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="255ea-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Dialogfeld "Front-End-Pools zuordnen"](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="255ea-129">Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie dann die Topologie.</span><span class="sxs-lookup"><span data-stu-id="255ea-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="255ea-130">Führen Sie die Schritte in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="255ea-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="255ea-131">Es ist sehr wichtig, dass Sie die Richtlinien in den Themen in der Bereitstellungsdokumentation befolgen.</span><span class="sxs-lookup"><span data-stu-id="255ea-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="255ea-132">Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar.</span><span class="sxs-lookup"><span data-stu-id="255ea-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="255ea-133">Sie sollten nun eine Legacy Edgeserver bereitstellen, die parallel mit einer Skype for Business Server 2019-Edge-Server-Bereitstellung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="255ea-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="255ea-134">Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren.</span><span class="sxs-lookup"><span data-stu-id="255ea-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

