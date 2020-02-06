---
title: Erstellen eines VIS-Pools in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Zusammenfassung: Erstellen eines Video-Interop-Server Pools in Skype for Business Server mithilfe des Topologie-Generators.'
ms.openlocfilehash: 474752253312b58b87a3d01f445bd93eabdaf203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798052"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="1e97a-103">Erstellen eines VIS-Pools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1e97a-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="1e97a-104">**Zusammenfassung:** Erstellen Sie einen Video-Interop-Serverpool in Skype for Business Server mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="1e97a-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="1e97a-105">Erstellen eines VIS oder VIS-Pools mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="1e97a-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="1e97a-106">Öffnen Sie den Topologie-Generator auf dem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1e97a-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="1e97a-107">Klicken Sie im linken Bereich des Topologie-Generators mit der rechten Maustaste auf **Video-Interop-Server Pools** , und wählen Sie **neuer Video-Interop-Server Pool**aus.</span><span class="sxs-lookup"><span data-stu-id="1e97a-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="1e97a-108">Dadurch wird ein Assistent zum **Erstellen eines neuen Video-Interop-Serverpools** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1e97a-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="1e97a-109">Geben Sie den Pool-FQDN für den neuen Video-Interop-Server ein, und wählen Sie entweder **dieser Pool hat einen Server** oder **dieser Pool verfügt über mehrere Server** basierend auf Ihrer Anforderung und dann **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="1e97a-110">Wenn Sie einen Video-Interop-Server Pool bereitstellen möchten, um eine höhere Verfügbarkeit zu gewährleisten, wählen Sie **dieser Pool hat mehrere Server**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="1e97a-111">Bedenken Sie bei dieser Option Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1e97a-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="1e97a-112">Sie müssen DNS-Lastenausgleich bereitstellen, um Video-Interop-Server Pools zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1e97a-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="1e97a-113">Geben Sie auf der nächsten Seite unter **Computer in diesem Pool definieren** im Textfeld den **Computer-FQDN** des jeweiligen Computers im Pool ein und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="1e97a-114">Wiederholen Sie diesen Schritt, um einen weiteren Video-Interop-Server zum Pool hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1e97a-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="1e97a-115">Wenn Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="1e97a-116">Wenn Sie nur einen Video-Interop-Server im Pool bereitstellen möchten, weil Sie keine höhere Verfügbarkeit benötigen, wählen Sie **diesen Pool hat einen Server** aus, und drücken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="1e97a-117">Wählen Sie in der Dropdownliste den nächsten Hoppool/FE aus und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="1e97a-118">Wählen Sie einen Edgepool aus, dem Sie den VIS zuordnen möchten, und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="1e97a-119">Legen Sie einen TCP- oder TLS-Port fest.</span><span class="sxs-lookup"><span data-stu-id="1e97a-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="1e97a-120">Wählen Sie im linken Bereich von Topology Builder den neu hinzugefügten Video-Interop-Server aus, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1e97a-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="1e97a-121">Aktivieren oder aktualisieren Sie den TCP- oder TLS-Port entsprechend Ihrer Anforderung und wählen Sie **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="1e97a-122">Obwohl TLS standardmäßig hinzugefügt wird, wurde nur TCP mit Cisco Unified Communications Manager (CallManager oder CUCM) vollständig getestet.</span><span class="sxs-lookup"><span data-stu-id="1e97a-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="1e97a-p106">Wählen Sie ein Videogateway aus. Erweitern Sie hierfür „Freigegebene Komponenten“, klicken Sie mit der rechten Maustaste auf **Videogateways** und wählen Sie **Neues Videogateway**.</span><span class="sxs-lookup"><span data-stu-id="1e97a-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="1e97a-p107">Geben Sie den FQDN des Videogateways oder die IP-Adresse ein. Das Videogateway kann sich in einer Unterdomäne oder einer anderen Domäne befinden. Der von den Videotelekonferenzgeräten Ihres Systems verwendete CUCM dient als Videogateway.</span><span class="sxs-lookup"><span data-stu-id="1e97a-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="1e97a-p108">Wählen Sie ggf. IPv4 oder IPv6 aus. Sie können alle konfigurierten IP-Adressen verwenden oder die Dienstnutzung auf die ausgewählten IP-Adressen beschränken.</span><span class="sxs-lookup"><span data-stu-id="1e97a-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="1e97a-130">Wählen Sie den Überwachungsport des Videogateways aus.</span><span class="sxs-lookup"><span data-stu-id="1e97a-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="1e97a-131">Wählen Sie das Transport Protokoll (TCP oder TLS) aus, und ordnen Sie es einem Video-Interop-Server zu, der für einen Video-SIP-Trunk eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="1e97a-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="1e97a-132">Das Transportprotokoll für das Videogateway sollte mit dem für den VIS konfigurierten Transportprotokoll übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1e97a-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="1e97a-133">Ein entsprechender Video-SIP-Trunk wird nach Abschluss des obigen Schritts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1e97a-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="1e97a-134">Klicken Sie mit der rechten Maustaste auf den Video-SIP-Trunk und wählen Sie den soeben hinzugefügten Trunk aus.</span><span class="sxs-lookup"><span data-stu-id="1e97a-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="1e97a-135">Der Name des Video-SIP-Trunks, der zugehörige Video-Interop-Server, das SIP-Transport Protokoll und der Port können alle geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1e97a-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="1e97a-136">Ein Video-Interop-Server unterstützt 1: N Trunks.</span><span class="sxs-lookup"><span data-stu-id="1e97a-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="1e97a-137">Daher können mehrere Trunks hinzugefügt werden, die einem einzelnen Video-Interop-Server zugeordnet sind, wobei jeder trunk auf einem anderen Video Gateway beendet wird.</span><span class="sxs-lookup"><span data-stu-id="1e97a-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="1e97a-138">Die Einschränkung besteht darin, dass ein bestimmtes Video Gateway nur einen trunk enthält, der für die Bereitstellung von Skype for Business Server definiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e97a-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="1e97a-139">Veröffentlichen Sie das Topologie-Dokument wie unter [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e97a-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e97a-140">Um die Widerstandsfähigkeit zu verbessern, können Sie einen zweiten Video-Interop-Server oder VIS-Pool oder einen Backup-Front-End-Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1e97a-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="1e97a-141">Weitere Informationen finden Sie unter [Resilienz-Mechanismen](../../plan-your-deployment/video-interop-server.md#resiliency) .</span><span class="sxs-lookup"><span data-stu-id="1e97a-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="1e97a-142">Alle mit dem Topologie-Generator ausgeführten Aufgaben sollten nun abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="1e97a-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="1e97a-143">Fahren Sie mit der Installation der Software auf dem neuen VIS-Server oder-Server fort.</span><span class="sxs-lookup"><span data-stu-id="1e97a-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="1e97a-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e97a-144">See also</span></span>

[<span data-ttu-id="1e97a-145">Bereitstellen der VIS-Serverrolle in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1e97a-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="1e97a-146">Planen des Video-Interop-Servers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1e97a-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="1e97a-147">Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e97a-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
