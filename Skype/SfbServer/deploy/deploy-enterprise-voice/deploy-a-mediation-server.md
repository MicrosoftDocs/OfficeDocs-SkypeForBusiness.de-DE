---
title: Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Zusammenfassung: Informationen Sie zum Definieren und Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015.'
ms.openlocfilehash: bfb915528ba73851d3bd60cc8ff3b33b968376e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="b0dba-103">Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b0dba-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b0dba-104">**Zusammenfassung:** Informationen Sie zum Definieren und Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b0dba-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b0dba-105">Die Enterprise-VoIP-Arbeitslast, einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (reaktionsgruppenanwendung, anrufparkanwendung, die anrufsteuerung (CAC) usw.) sind in Front-End-Pools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b0dba-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="b0dba-106">Die Funktionalität des Vermittlungsservers ist in der Front-End-Server integriert.</span><span class="sxs-lookup"><span data-stu-id="b0dba-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="b0dba-107">Einen separaten eigenständigen Vermittlungsserver ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b0dba-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="b0dba-108">Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar.</span><span class="sxs-lookup"><span data-stu-id="b0dba-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="b0dba-109">Zum Verbinden Ihrer Enterprise-VoIP-Infrastruktur mit SIP-Trunk-Dienstanbieter müssen einen getrennten Vermittlungsserver bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0dba-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="b0dba-110">Die Verbindung zwischen Skype für Business Server (entweder ein Vermittlungsserver gemeinsam auf einem Front-End-Pool oder den eigenständigen Vermittlungsserver ausgeführt) und einem Gateway wird als eine logische Zuordnung mit dem Namen eines Trunks definiert.</span><span class="sxs-lookup"><span data-stu-id="b0dba-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="b0dba-111">In den Themen in diesem Abschnitt beschreiben einen Trunk zu definieren und wie Sie einen eigenständigen Vermittlungsserver bereitstellen, wenn Sie einen SIP-Trunk herstellen.</span><span class="sxs-lookup"><span data-stu-id="b0dba-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="b0dba-112">Definieren eines Vermittlungsservers im Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="b0dba-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="b0dba-113">Sie können Vermittlungsserver als auf einem Front-End-Pool verbundenen Rolle hinzufügen oder ein separates eigenständigen vermittlungsserverpool definieren.</span><span class="sxs-lookup"><span data-stu-id="b0dba-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="b0dba-114">So fügen Sie einen Vermittlungsserver auf einem Front-End-Pool hinzu</span><span class="sxs-lookup"><span data-stu-id="b0dba-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="b0dba-115">Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b0dba-116">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website für die Sie einen Front-End-Pool definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b0dba-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="b0dba-117">In der Konsolenstruktur mit der rechten Maustaste in des Typs des gewünschten Front-End-Pool, und klicken Sie dann auf **neue Front-End-Pool..**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="b0dba-118">Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.</span><span class="sxs-lookup"><span data-stu-id="b0dba-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="b0dba-119">**Verbundene Serverrollen auswählen**aktivieren Sie die Option **Mediation Server verbinden**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0dba-120">Wenn der Typ des Front-End-Pools, den Sie ausgewählt haben die Enterprise Edition ist, dann wird die Mediation Server-Komponente auf allen Front-End-Servern von diesem Front-End-Pool installiert.</span><span class="sxs-lookup"><span data-stu-id="b0dba-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="b0dba-121">**Nächster hoppool** vom Vermittlungsserver verwendet werden den Front-End-Pool, in dem der Vermittlungsserver verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b0dba-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="b0dba-122">Der **Edge-Pool** für die vom Vermittlungsserver werden auf den gleichen Edge-Pool verknüpft ist, mit dem Front-End-Pool, in dem der Vermittlungsserver verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b0dba-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="b0dba-123">Klicken Sie auf **Als Standardeinstellung festlegen** , um diesem Front-End-Pool verwenden, um Anrufe an das Telefonfestnetz weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="b0dba-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="b0dba-124">Klicken Sie auf **Fertig stellen** , wenn Sie einen oder mehrere Peers auf den Front-End-Pool zuordnen fertig sind.</span><span class="sxs-lookup"><span data-stu-id="b0dba-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0dba-125">Bevor Sie mit dem nächsten Schritt des Bereitstellungsprozesses für Enterprise-VoIP fortfahren, stellen Sie sicher, dass der Mediation Server-Pool (d. h. Front-End-Pool mit der Komponente Vermittlungsserver gemeinsam ausgeführt) die FQDNs verwendet, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="b0dba-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="b0dba-126">Maustaste auf den Knoten **Skype für Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="b0dba-127">So fügen Sie einen eigenständigen Vermittlungsserver hinzu</span><span class="sxs-lookup"><span data-stu-id="b0dba-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="b0dba-128">Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b0dba-129">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website für die Sie einen Vermittlungsserver definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b0dba-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="b0dba-130">In der Konsolenstruktur mit der rechten Maustaste in des Knotens **vermittlungspools** , und klicken Sie dann auf **vermittlungsserverpool**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="b0dba-131">Geben Sie im **Neuen Vermittlungspool definieren**den Vermittlungsserver Pool vollqualifizierten Domänennamen (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b0dba-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="b0dba-132">Führen Sie anschließend eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="b0dba-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="b0dba-133">Wenn Sie mehrere Vermittlungsserver im Pool, um hohe Verfügbarkeit bereitstellen möchten, wählen Sie **Pool mit mehreren Computern**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0dba-134">Sie müssen bereitstellen (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) vermittlungsserverpools unterstützt, die mehrere Mediation Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0dba-134">You must deploy  (../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="b0dba-135">Wenn Sie nur einen Vermittlungsserver im Pool bereitstellen, da Sie keine hohe Verfügbarkeit erforderlich möchten, wählen Sie **Pool mit einem Computer**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="b0dba-136">Überspringen Sie den folgenden Schritt.</span><span class="sxs-lookup"><span data-stu-id="b0dba-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="b0dba-137">Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="b0dba-138">Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0dba-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="b0dba-139">Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="b0dba-140">Klicken Sie auf der Seite **Auswählen des nächsten Hops** klicken Sie auf **Nächster hoppool**, klicken Sie auf den FQDN des Front-End-Pools, die diesem Pool Mediation Server verwenden, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b0dba-141">Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b0dba-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="b0dba-142">Wenn Sie PSTN-Konnektivität für externe Benutzer für Enterprise-VoIP aktiviert bereitstellen möchten unter **Wählen Sie Edgepool, die von diesem Vermittlungsserver verwendet wird**, klicken Sie auf den FQDN des Edge-Server-Pools, der diesen Mediation Server-Pool verwendet wird, um PSTN-Anbindung zu bieten Diese externen Benutzer, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="b0dba-143">Wenn Sie nicht vorhaben, damit externe Benutzer für Enterprise-VoIP können oder nicht PSTN-Anbindung für Benutzer bereitstellen, wenn sie außerhalb des internen Netzwerks sind möchten, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="b0dba-144">Maustaste auf den Knoten **Skype für Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="b0dba-145">Definieren Sie die Mediation Server überwacht Ports</span><span class="sxs-lookup"><span data-stu-id="b0dba-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="b0dba-146">Führen Sie die Schritte in diesem Thema zum Topologie-Generator verwenden, um die Überwachungsports Definieren eines Vermittlungsservers oder Pool werden eingehende Verbindungen von einem gatewaypeer akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b0dba-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="b0dba-147">So ändern Sie die Mediation Server überwacht Ports</span><span class="sxs-lookup"><span data-stu-id="b0dba-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="b0dba-148">Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.</span><span class="sxs-lookup"><span data-stu-id="b0dba-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b0dba-149">Im Topologie-Generator, in der Konsolenstruktur erweitern Sie den Knoten **vermittlungspools** , und mit der rechten Maustaste in den zuvor erstellten Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="b0dba-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="b0dba-150">Standardmäßig sind die SIP-Überwachungsports auf dem Vermittlungsserver für TLS-Datenverkehr von Skype für Business Server 5070 und 5067 für TLS-Datenverkehr von Kollegen (z. B. Gateways, PBXes oder SBCs).</span><span class="sxs-lookup"><span data-stu-id="b0dba-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="b0dba-151">Der TCP-Port ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b0dba-151">TCP port is disabled by default.</span></span> <span data-ttu-id="b0dba-152">Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b0dba-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="b0dba-153">Geben Sie die gewünschten TLS oder TCP-überwachungsportbereich der Vermittlungsserver eingehende Verbindungen von PSTN-Gateways akzeptiert wird.</span><span class="sxs-lookup"><span data-stu-id="b0dba-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0dba-p107">Wenn die Option **TCP-Port aktivieren** nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.</span><span class="sxs-lookup"><span data-stu-id="b0dba-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

