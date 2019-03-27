---
title: Erstellen eines Pools gegenüber in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Zusammenfassung: Erstellen Sie einen Video Interop-Serverpool in Skype für Business Server mithilfe des Topologie-Generator.'
ms.openlocfilehash: 484cb1c504680dde393d24ce65606e415d070edb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874109"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="8702c-103">Erstellen eines Pools gegenüber in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8702c-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="8702c-104">**Zusammenfassung:** Erstellen Sie einen Video Interop-Serverpool in Skype für Business Server mithilfe des Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="8702c-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="8702c-105">Erstellen eines VIS oder VIS-Pools mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="8702c-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="8702c-106">Öffnen Sie den Topologie-Generator auf dem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="8702c-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="8702c-107">Klicken Sie im linken Bereich des Topologie-Generator klicken Sie mit der rechten Maustaste auf **Video Interop-Server-Pools** , und wählen Sie **Neue Video Interop-Serverpool**.</span><span class="sxs-lookup"><span data-stu-id="8702c-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="8702c-108">Ein Assistenten zum **Erstellen einer neuen Video Interop-Serverpool** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8702c-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="8702c-109">Geben Sie den Pool-FQDN für den neuen Video Interop-Server, und wählen Sie entweder **diesem Pool einen Server** oder **Pool verfügt über mehrere Server** basierend auf Ihrer Anforderung aus, drücken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8702c-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="8702c-110">Wenn Sie einen Video Interop-Serverpool, um hohe Verfügbarkeit bereitstellen möchten, wählen Sie **in diesem Pool verfügt über mehrere Server**.</span><span class="sxs-lookup"><span data-stu-id="8702c-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="8702c-111">Bedenken Sie bei dieser Option Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8702c-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="8702c-112">Sie müssen die DNS-Lastenausgleich zur Unterstützung von Video Interop-Server-Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8702c-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="8702c-113">Geben Sie auf der nächsten Seite unter **Computer in diesem Pool definieren** im Textfeld den **Computer-FQDN** des jeweiligen Computers im Pool ein und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8702c-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="8702c-114">Wiederholen Sie diesen Schritt, um einen weiteren Video Interop Server zum Pool hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8702c-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="8702c-115">Wenn Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8702c-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="8702c-116">Wenn Sie nur ein Video Interop-Server im Pool bereitstellen, da Sie keine hohe Verfügbarkeit erforderlich möchten, wählen Sie **in diesem Pool hat einen Server** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8702c-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="8702c-117">Wählen Sie in der Dropdownliste den nächsten Hoppool/FE aus und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8702c-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="8702c-118">Wählen Sie einen Edgepool aus, dem Sie den VIS zuordnen möchten, und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="8702c-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="8702c-119">Legen Sie einen TCP- oder TLS-Port fest.</span><span class="sxs-lookup"><span data-stu-id="8702c-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="8702c-120">Wählen Sie den neu hinzugefügten Video Interop-Server aus der Topologie-Generator im linken, klicken Sie rechten Maustaste darauf, und wählen Sie **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8702c-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="8702c-121">Aktivieren oder aktualisieren Sie den TCP- oder TLS-Port entsprechend Ihrer Anforderung und wählen Sie **OK**.</span><span class="sxs-lookup"><span data-stu-id="8702c-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="8702c-122">Obwohl standardmäßig TLS hinzugefügt wurde, wurde nur TCP vollständig mit Cisco Unified Communications Manager (CallManager oder CUCM) getestet.</span><span class="sxs-lookup"><span data-stu-id="8702c-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="8702c-p106">Wählen Sie ein Videogateway aus. Erweitern Sie hierfür „Freigegebene Komponenten“, klicken Sie mit der rechten Maustaste auf **Videogateways** und wählen Sie **Neues Videogateway**.</span><span class="sxs-lookup"><span data-stu-id="8702c-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="8702c-p107">Geben Sie den FQDN des Videogateways oder die IP-Adresse ein. Das Videogateway kann sich in einer Unterdomäne oder einer anderen Domäne befinden. Der von den Videotelekonferenzgeräten Ihres Systems verwendete CUCM dient als Videogateway.</span><span class="sxs-lookup"><span data-stu-id="8702c-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="8702c-p108">Wählen Sie ggf. IPv4 oder IPv6 aus. Sie können alle konfigurierten IP-Adressen verwenden oder die Dienstnutzung auf die ausgewählten IP-Adressen beschränken.</span><span class="sxs-lookup"><span data-stu-id="8702c-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="8702c-130">Wählen Sie den Überwachungsport des Videogateways aus.</span><span class="sxs-lookup"><span data-stu-id="8702c-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="8702c-131">Wählen Sie das Transportprotokoll (TCP oder TLS), und verknüpfen Sie ihn mit einem Video Interop-Server, der für einen SIP-Trunk video eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="8702c-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="8702c-132">Das Transportprotokoll für das Videogateway sollte mit dem für den VIS konfigurierten Transportprotokoll übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8702c-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="8702c-133">Ein entsprechender Video-SIP-Trunk wird nach Abschluss des obigen Schritts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8702c-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="8702c-134">Klicken Sie mit der rechten Maustaste auf den Video-SIP-Trunk und wählen Sie den soeben hinzugefügten Trunk aus.</span><span class="sxs-lookup"><span data-stu-id="8702c-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="8702c-135">Die video-SIP-Trunk-Name, Video Interop-Server-SIP-Transportprotokoll zugeordnet und kann alle Port geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8702c-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="8702c-136">Ein Video Interop-Server unterstützt 1: n-Trunks.</span><span class="sxs-lookup"><span data-stu-id="8702c-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="8702c-137">Daher können mehrere Trunks die zugeordnet, mit einem einzelnen Server zur Video-Interop, wobei jeden Trunk auf einem anderen Video Gateway beendet werden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8702c-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="8702c-138">Die Einschränkung ist einem bestimmten Gateway Video nur einen einzigen Trunk verfügt, die an die Skype für Business Server-Bereitstellung definiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8702c-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="8702c-139">Veröffentlichen Sie das Topologiedokument gemäß [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="8702c-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8702c-140">Um ausfallsicherheit zu verbessern, sollten Sie einen zweiten Interop Videoserver oder gegenüber Pool oder einem Front-End-Sicherungspool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8702c-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="8702c-141">Weitere Informationen finden Sie unter [Resiliency Mechanismen](../../plan-your-deployment/video-interop-server.md#resiliency) .</span><span class="sxs-lookup"><span data-stu-id="8702c-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="8702c-142">Alle Aufgaben des Topologie-Generators sollte jetzt abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="8702c-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="8702c-143">Wechseln Sie zum Installieren der Software auf den neuen gegenüber oder die Server.</span><span class="sxs-lookup"><span data-stu-id="8702c-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="8702c-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8702c-144">See also</span></span>

[<span data-ttu-id="8702c-145">Bereitstellen der Serverrolle gegenüber in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8702c-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="8702c-146">Planen der Interop-Videoserver in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8702c-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="8702c-147">Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8702c-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
