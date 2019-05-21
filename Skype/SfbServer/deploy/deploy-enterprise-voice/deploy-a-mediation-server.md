---
title: Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen Vermittlungs Server im Topologie-Generator in Skype for Business Server definieren und bereitstellen.'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284648"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="6f2af-103">Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6f2af-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="6f2af-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Vermittlungs Server im Topologie-Generator in Skype for Business Server definieren und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6f2af-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="6f2af-105">Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (reaktionsgruppenanwendung, Anruf Park Anwendung, Anrufsteuerung (CAC) usw.) stehen in Front-End-Pools zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6f2af-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="6f2af-106">Die Funktionalität des Vermittlungsservers ist in den Front-End-Server integriert.</span><span class="sxs-lookup"><span data-stu-id="6f2af-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="6f2af-107">Ein separater eigenständiger Vermittlungs Server ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6f2af-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="6f2af-108">Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar.</span><span class="sxs-lookup"><span data-stu-id="6f2af-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="6f2af-109">Wenn Sie Ihre Enterprise-VoIP-Infrastruktur mit Ihrem SIP-Trunk-Anbieter verbinden möchten, muss ein separater Vermittlungs Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6f2af-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="6f2af-110">Die Verbindung zwischen Skype for Business Server (einem Vermittlungsserver, der sich auf einem Front-End-Pool oder einem eigenständigen Vermittlungsserver befindet) und einem Gateway wird als logische Assoziation namens "Trunk" definiert.</span><span class="sxs-lookup"><span data-stu-id="6f2af-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="6f2af-111">In den Themen in diesem Abschnitt wird beschrieben, wie Sie einen trunk definieren und wie Sie einen eigenständigen Vermittlungs Server bereitstellen, wenn Sie eine Verbindung mit einem SIP-Stamm herstellen.</span><span class="sxs-lookup"><span data-stu-id="6f2af-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="6f2af-112">Definieren eines Vermittlungsservers im Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="6f2af-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="6f2af-113">Sie können Mediation Server als zusammenhängende Rolle in einem Front-End-Pool hinzufügen oder einen separaten eigenständigen vermittlungsserverpool definieren.</span><span class="sxs-lookup"><span data-stu-id="6f2af-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="6f2af-114">So fügen Sie einen Vermittlungs Server zu einem Front-End-Pool hinzu</span><span class="sxs-lookup"><span data-stu-id="6f2af-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="6f2af-115">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="6f2af-116">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie einen Front-End-Pool definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6f2af-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="6f2af-117">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Typ des gewünschten Front-End-Pools, und klicken Sie dann auf **neuer Front-End-Pool.**..</span><span class="sxs-lookup"><span data-stu-id="6f2af-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="6f2af-118">Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.</span><span class="sxs-lookup"><span data-stu-id="6f2af-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="6f2af-119">Aktivieren Sie unter **ausgewählte Serverrollen auswählen**die Option **Collocate-Vermittlungsserver**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f2af-120">Wenn der Typ des ausgewählten Front-End-Pools die Enterprise-Edition ist, wird die Mediation Server-Komponente auf allen Front-End-Servern dieses Front-End-Pools installiert.</span><span class="sxs-lookup"><span data-stu-id="6f2af-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="6f2af-121">Der vom Vermittlungsserver verwendete **Next Hop-Pool** ist der Front-End-Pool, in dem sich der Vermittlungsserver befindet.</span><span class="sxs-lookup"><span data-stu-id="6f2af-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="6f2af-122">Der vom Vermittlungsserver verwendete **Edge-Pool** ist derselbe Edge-Pool, der dem Front-End-Pool zugeordnet ist, in dem sich der Vermittlungsserver befindet.</span><span class="sxs-lookup"><span data-stu-id="6f2af-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="6f2af-123">Klicken Sie auf als **Standard festlegen** , um diesen Front-End-Pool zum Weiterleiten von Anrufen an das PSTN zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f2af-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="6f2af-124">Klicken Sie auf **Fertig stellen** , wenn Sie mit dem Verknüpfen eines oder mehrerer Peers mit dem Front-End-Pool fertig sind.</span><span class="sxs-lookup"><span data-stu-id="6f2af-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f2af-125">Bevor Sie mit dem nächsten Schritt des Enterprise-VoIP-Bereitstellungsprozesses fortfahren, stellen Sie sicher, dass der vermittlungsserverpool (also der Front-End-Pool mit der Mediationsserver Komponente) die von Ihnen angegebenen FQDNs verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f2af-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="6f2af-126">Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="6f2af-127">So fügen Sie einen eigenständigen Vermittlungsserver hinzu</span><span class="sxs-lookup"><span data-stu-id="6f2af-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="6f2af-128">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="6f2af-129">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie einen Vermittlungs Server definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6f2af-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="6f2af-130">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten **Mediations Pools** , und klicken Sie dann auf **Vermittlungs Server Pool**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="6f2af-131">Geben Sie unter **neuen Mediations Pool definieren**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Mediation Server Pools ein.</span><span class="sxs-lookup"><span data-stu-id="6f2af-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="6f2af-132">Führen Sie anschließend eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6f2af-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="6f2af-133">Wenn Sie mehrere Vermittlungsserver im Pool bereitstellen möchten, um eine höhere Verfügbarkeit zu gewährleisten, wählen Sie den **Pool für mehrere Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="6f2af-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6f2af-134">Sie müssen [Bereitstellen](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) , um Vermittlungsserver Pools mit mehreren Vermittlungsservern zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6f2af-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="6f2af-135">Wenn Sie nur einen Vermittlungs Server im Pool bereitstellen möchten, weil Sie keine höhere Verfügbarkeit benötigen, wählen Sie den **Pool für einzelne Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="6f2af-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="6f2af-136">Überspringen Sie den folgenden Schritt.</span><span class="sxs-lookup"><span data-stu-id="6f2af-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="6f2af-137">Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="6f2af-138">Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="6f2af-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="6f2af-139">Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="6f2af-140">Klicken Sie auf der Seite **Nächster Hop auswählen** auf **Nächster Hop-Pool**, klicken Sie auf den FQDN des Front-End-Pools, in dem dieser Vermittlungs Server Pool verwendet wird, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="6f2af-141">Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6f2af-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="6f2af-142">Wenn Sie die PSTN-Konnektivität für externe Benutzer bereitstellen möchten, die für Enterprise-VoIP aktiviert sind, klicken Sie unter Wählen Sie den **von diesem Vermittlungsserver verwendeten Edge-Pool**aus auf den FQDN des Edgeserver-Pools, der diesen vermittlungsserverpool verwendet, um die PSTN-Konnektivität für Diese externen Benutzer aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="6f2af-143">Wenn Sie nicht beabsichtigen, externe Benutzer für Enterprise-VoIP zu aktivieren, oder wenn Sie keine PSTN-Konnektivität für Benutzer bereitstellen möchten, wenn diese sich außerhalb des internen Netzwerks befinden, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="6f2af-144">Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="6f2af-145">Definieren der Abhör Anschlüsse des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="6f2af-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="6f2af-146">Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators die Abhör Anschlüsse zu definieren, die von einem Vermittlungs Server oder-Pool eingehende Verbindungen von einem Gateway-Peer akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f2af-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="6f2af-147">So ändern Sie die Abhör Anschlüsse des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="6f2af-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="6f2af-148">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="6f2af-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="6f2af-149">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Knoten **Mediations Pools** , und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Mediations Server.</span><span class="sxs-lookup"><span data-stu-id="6f2af-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="6f2af-150">Standardmäßig sind die SIP-Abhör Anschlüsse auf dem Vermittlungsserver 5070 für den TLS-Datenverkehr von Skype for Business Server und 5067 für TLS-Datenverkehr von Peers (wie Gateways, TK oder SBCS).</span><span class="sxs-lookup"><span data-stu-id="6f2af-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="6f2af-151">Der TCP-Port ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f2af-151">TCP port is disabled by default.</span></span> <span data-ttu-id="6f2af-152">Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6f2af-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="6f2af-153">Geben Sie den gewünschten TLS-oder TCP-Überwachungs Portbereich an der Vermittlungs Server akzeptiert eingehende Verbindungen von PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="6f2af-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f2af-p107">Wenn die Option **TCP-Port aktivieren** nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.</span><span class="sxs-lookup"><span data-stu-id="6f2af-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

