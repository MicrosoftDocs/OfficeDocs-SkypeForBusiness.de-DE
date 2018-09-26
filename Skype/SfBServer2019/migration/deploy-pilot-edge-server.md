---
title: Bereitstellen von pilot Edge-Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Thema werden die Konfigurationseinstellungen, die Sie kennen sollten, bevor Sie Ihre Skype für Business Server 2019 Edge-Server bereitstellen müssen. Die Bereitstellung und Konfiguration Prozesse für Skype für Business Server 2019 sind Skype für Business Server 2015 sehr ähnlich. In diesem Abschnitt werden nur die wichtigsten Punkte, die Sie als Teil Ihrer Bereitstellung eines pilotpools berücksichtigen sollten. Ausführliche Schritte finden Sie unter Deploying Zugriff durch externe Benutzer in Skype für Business Server 2019 in der Bereitstellungsdokumentation, wird der Bereitstellungsprozess beschrieben und bietet auch Konfigurationsinformationen für den Zugriff externer Benutzer.
ms.openlocfilehash: 3ae1508c56ac3240cfb9904415090ff1bdf18677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029860"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="70632-106">Bereitstellen von pilot Edge-Server</span><span class="sxs-lookup"><span data-stu-id="70632-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="70632-107">In diesem Thema werden die Konfigurationseinstellungen, die, denen Sie berücksichtigen sollten vor der Bereitstellung von Ihrer Skype für Business Server 2019 Edge-Server, behandelt.</span><span class="sxs-lookup"><span data-stu-id="70632-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="70632-108">Die Bereitstellung und Konfiguration Prozesse für Skype für Business Server 2019 sind Skype für Business Server 2015 sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="70632-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="70632-109">In diesem Abschnitt werden nur die wichtigsten Punkte, die Sie als Teil Ihrer Bereitstellung eines pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="70632-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="70632-110">Navigieren Sie durch den Assistenten **Neuen Edgepool definieren** , überprüfen Sie die wichtigsten Konfigurationseinstellungen in den folgenden Schritten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="70632-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="70632-111">Beachten Sie, dass nur ein paar Seiten des Assistenten **Neues Edge-Pool definieren** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="70632-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="70632-112">So definieren Sie einen Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="70632-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="70632-113">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="70632-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="70632-114">Navigieren Sie zu der Skype für Business Server 2019 Knoten.</span><span class="sxs-lookup"><span data-stu-id="70632-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="70632-115">Maustaste auf **edgepools**, und klicken Sie auf **Neuer edgepool**.</span><span class="sxs-lookup"><span data-stu-id="70632-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Das Dialogfeld neuen Edgepool definieren](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="70632-117">Ein edgepool kann es sich um einen **Pool mit mehreren Computern** oder **Pool mit einem Computer**sein.</span><span class="sxs-lookup"><span data-stu-id="70632-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Definieren der Edge-Pool-FQDN (Dialogfeld)](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="70632-119">Aktivieren Sie auf der Seite **Features auswählen** nicht verbunden oder XMPP-Verbund.</span><span class="sxs-lookup"><span data-stu-id="70632-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="70632-120">Verbund und XMPP-Verbund werden beide derzeit über Edgeserver der Vorversion weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="70632-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="70632-121">Diese Funktionen werden in einer späteren Phase der Migration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="70632-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="70632-122">Weiterhin die folgenden Seiten des Assistenten ausfüllen: **Externe FQDNs**, **die interne IP-Adresse definieren**und **die externe IP-Adresse definieren**.</span><span class="sxs-lookup"><span data-stu-id="70632-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="70632-123">Wählen Sie auf der Seite **Server für den nächsten Hop definieren** den Director für den nächsten Hop des edgepool der Vorgängerversion.</span><span class="sxs-lookup"><span data-stu-id="70632-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Definieren der nächsten Hop (Dialogfeld)](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="70632-125">Auf der Seite **Front-End zuordnen oder vermittlungspools** nicht zuordnen eines Pools mit diesen edgepool zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="70632-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="70632-126">Externe Mediendatenverkehr wird derzeit über Edgeserver der Vorversion geleitet.</span><span class="sxs-lookup"><span data-stu-id="70632-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="70632-127">Diese Einstellung wird in einer späteren Phase der Migration konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="70632-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Ordnen Sie im Dialogfeld Front-End-Pools](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="70632-129">Klicken Sie auf **Fertig stellen**, und klicken Sie dann **Veröffentlichen** der Topologie.</span><span class="sxs-lookup"><span data-stu-id="70632-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="70632-130">Führen Sie die Schritte in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edge-Server installieren, Zertifikate zu konfigurieren und Starten der Dienste aus.</span><span class="sxs-lookup"><span data-stu-id="70632-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="70632-131">Es ist sehr wichtig, dass die Einhaltung der Richtlinien in den Themen in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="70632-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="70632-132">In diesem Abschnitt Exportvorgängen lediglich einige Hinweise auf Konfigurationseinstellungen für diese Serverrollen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="70632-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="70632-133">Sie haben jetzt einen legacy Edge-Server parallel mit einer Skype für Business Server 2019 Edge-Server-Bereitstellung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="70632-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="70632-134">Stellen Sie sicher, dass sowohl Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie beide Bereitstellungen vor dem Verschieben in die nächste Phase verwalten können.</span><span class="sxs-lookup"><span data-stu-id="70632-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

