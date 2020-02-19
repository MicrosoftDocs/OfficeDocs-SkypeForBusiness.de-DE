---
title: 'Lync Server 2013: Definieren eines Vermittlungsserver im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0109a7091870b7409fd9bc20b9de3abd3b2f3a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="9584e-102">Definieren eines Vermittlungsserver im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9584e-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9584e-103">_**Letztes Änderungsstand des Themas:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="9584e-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="9584e-104">Befolgen Sie die Schritte in diesem Thema, um mithilfe des Topologie-Generators eine eigenständige Vermittlungsserver oder einen Pool mit einer Front-End-Pool an einem Standort zu definieren, für den Sie Enterprise-VoIP zuvor nicht bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="9584e-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="9584e-105">Sie können eine Topologie auch über ein Konto definieren, das Mitglied der Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="9584e-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="9584e-106">Definieren Vermittlungsserver zusammen mit einem Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="9584e-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="9584e-107">Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators eine Vermittlungsserver zu definieren, die mit einem Front-End-Pool an einem Standort verbunden ist, an dem Enterprise-VoIP noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9584e-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="9584e-108">So fügen Sie einem Front-End-Pool ein Vermittlungsserver hinzu</span><span class="sxs-lookup"><span data-stu-id="9584e-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="9584e-109">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="9584e-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9584e-110">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie eine Front-End-Pool definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9584e-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="9584e-111">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den gewünschten Front-End-Pooltyp, und klicken Sie dann auf **neue Front-End-Pool.**..</span><span class="sxs-lookup"><span data-stu-id="9584e-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="9584e-112">Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.</span><span class="sxs-lookup"><span data-stu-id="9584e-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="9584e-113">Aktivieren Sie unter verbundene **Serverrollen auswählen**die Option **Collocate Vermittlungsserver**.</span><span class="sxs-lookup"><span data-stu-id="9584e-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="9584e-114">Wenn es sich bei dem ausgewählten Front-End-Pool um die Enterprise Edition handelt, wird die Vermittlungsserver-Komponente auf allen Front-End-Servern dieses Front-End-Pool installiert.</span><span class="sxs-lookup"><span data-stu-id="9584e-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9584e-115">Der <STRONG>nächste Hop-Pool</STRONG> , der von der Vermittlungsserver verwendet wird, ist der Front-End-Pool, in dem die Vermittlungsserver zusammengefasst ist.</span><span class="sxs-lookup"><span data-stu-id="9584e-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9584e-116">Der <STRONG>Edgepool</STRONG> , der von der Vermittlungsserver verwendet wird, ist derselbe Edgepool, der dem Front-End-Pool zugeordnet ist, in dem die Vermittlungsserver zusammengefasst ist.</span><span class="sxs-lookup"><span data-stu-id="9584e-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="9584e-117">Klicken Sie auf **Standard festlegen** , um diese Front-End-Pool zum Weiterleiten von Anrufen von Microsoft Office Communications Server 2007 R2 an das PSTN zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9584e-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="9584e-118">Klicken Sie auf **Fertig stellen** , wenn Sie dem Front-End-Pool das Zuordnen eines oder mehrerer Peers abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="9584e-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9584e-119">Bevor Sie mit dem nächsten Schritt im Enterprise-VoIP-Bereitstellungsprozess fortfahren, stellen Sie sicher, dass der Vermittlungsserver-Pool (d. h. Front-End-Pool mit der Vermittlungsserver-Komponente nebeneinander) die von Ihnen angegebenen FQDNs verwendet.</span><span class="sxs-lookup"><span data-stu-id="9584e-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="9584e-120">Befolgen Sie anschließend die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) im Bereitstellungshandbuch, um die Vermittlungsserver zu Ihrer Topologie hinzuzufügen, bevor Sie mit dem nächsten Schritt der Änderung der Überwachungs Ports des Vermittlungsserver falls erforderlich fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9584e-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="9584e-121">Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um die Topologie zu definieren oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9584e-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="9584e-122">Eigenständige Vermittlungsserver definieren</span><span class="sxs-lookup"><span data-stu-id="9584e-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="9584e-123">Befolgen Sie die Schritte in diesem Thema, um mithilfe des Topologie-Generators einen eigenständigen Vermittlungsserver oder Pool an einem Standort zu definieren, an dem Enterprise-VoIP noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9584e-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="9584e-124">Wenn Sie bereits Vermittlungsserver in einem Front-End-Pool an diesem Standort bereitgestellt haben, können Sie diesen Abschnitt überspringen und [die Dateien für Vermittlungsserver in lync Server 2013 installieren](lync-server-2013-install-the-files-for-mediation-server.md) , bevor Sie mit dem [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9584e-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9584e-125">In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens eine Front-End-Pool eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Dokumentation zum Bereitstellungshandbuch beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9584e-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="9584e-126">So fügen Sie einen Vermittlungsserver hinzu</span><span class="sxs-lookup"><span data-stu-id="9584e-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="9584e-127">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="9584e-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9584e-128">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie eine Vermittlungsserver definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9584e-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="9584e-129">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten **Vermittlungs Pools** , und klicken Sie dann auf **Vermittlungsserver Pool**.</span><span class="sxs-lookup"><span data-stu-id="9584e-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="9584e-130">Geben Sie unter **neuen vermittlungspool definieren**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Vermittlungsserver Pools ein.</span><span class="sxs-lookup"><span data-stu-id="9584e-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="9584e-131">Führen Sie anschließend eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9584e-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="9584e-132">Wenn Sie mehrere Vermittlungsserver im Pool bereitstellen möchten, um eine hohe Verfügbarkeit bereitzustellen, wählen Sie **Pool mit mehreren Computern**aus.</span><span class="sxs-lookup"><span data-stu-id="9584e-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9584e-133">Sie müssen den DNS-Lastenausgleich bereitstellen, um Vermittlungsserver Pools zu unterstützen, die über mehrere Vermittlungsserver verfügen.</span><span class="sxs-lookup"><span data-stu-id="9584e-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="9584e-134">Ausführliche Informationen finden Sie im Abschnitt Verwenden des DNS-Lastenausgleichs in Vermittlungsserver Pools des <A href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleichs in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9584e-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="9584e-135">Wenn Sie nur eine Vermittlungsserver im Pool bereitstellen möchten, da keine hohe Verfügbarkeit erforderlich ist, wählen Sie **Pool mit einem einzelnen Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="9584e-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="9584e-136">Überspringen Sie den folgenden Schritt.</span><span class="sxs-lookup"><span data-stu-id="9584e-136">Skip the following step.</span></span>

6.  <span data-ttu-id="9584e-137">Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein, und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9584e-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="9584e-138">Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9584e-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="9584e-139">Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9584e-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="9584e-140">Klicken Sie auf der Seite **nächsten Hop auswählen** auf **Pool für nächsten**Hop, klicken Sie auf den FQDN des Front-End-Pool, in dem dieser Vermittlungsserver Pool verwendet wird, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9584e-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="9584e-141">Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9584e-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9584e-142">Wenn Sie PSTN-Konnektivität für für Enterprise-VoIP aktivierte externe Benutzer bereitstellen möchten, klicken Sie unter **Edge-Pool auswählen, der von diesem Vermittlungsserver verwendet**wird auf den FQDN des Edgeserver Pools, der diesen Vermittlungsserver Pool verwendet, um PSTN-Konnektivität für diese externen Benutzer bereitzustellen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9584e-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="9584e-143">Wenn Sie nicht beabsichtigen, externe Benutzer für Enterprise-VoIP zu aktivieren oder wenn Sie keine PSTN-Konnektivität für Benutzer bereitstellen möchten, die sich außerhalb des internen Netzwerks befinden, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9584e-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="9584e-144">Befolgen Sie anschließend die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation, um die Vermittlungsserver der Topologie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9584e-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="9584e-145">Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um die Topologie zu erstellen oder zu ändern, damit die Daten für die Installation der Dateien für Server mit lync Server verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9584e-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="9584e-146">Fahren Sie dann mit den nächsten Schritten zum Ändern der Überwachungsports auf dem Vermittlungsserver fort (sofern erforderlich).</span><span class="sxs-lookup"><span data-stu-id="9584e-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="9584e-147">Definieren der Vermittlungsserver Abhör-Ports</span><span class="sxs-lookup"><span data-stu-id="9584e-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="9584e-148">Befolgen Sie die Schritte in diesem Thema, um mithilfe des Topologie-Generators die Überwachungs Ports zu definieren, die ein Vermittlungsserver oder Pool eingehende Verbindungen von einem Gateway-Peer akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9584e-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="9584e-149">So ändern Sie die Vermittlungsserver Abhör-Ports</span><span class="sxs-lookup"><span data-stu-id="9584e-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="9584e-150">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="9584e-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9584e-151">Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Knoten **Vermittlungs Pools** , und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="9584e-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="9584e-152">Standardmäßig sind die SIP-Überwachungsanschlüsse am Vermittlungsserver 5070 für den TLS-Datenverkehr von lync Server, 5067 für TLS-Datenverkehr von Peers (Gateways, TK oder SBCS).</span><span class="sxs-lookup"><span data-stu-id="9584e-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="9584e-153">Der TCP-Port ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9584e-153">TCP port is disabled by default.</span></span> <span data-ttu-id="9584e-154">Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9584e-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="9584e-155">Geben Sie den gewünschten TLS-oder TCP-Überwachungs Portbereich an, der vom Vermittlungsserver eingehende Verbindungen von PSTN-Gateways akzeptiert wird.</span><span class="sxs-lookup"><span data-stu-id="9584e-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9584e-156">Wenn die Option <STRONG>TCP-Port aktivieren</STRONG> nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9584e-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="9584e-157">Diese Einstellung ist optional.</span><span class="sxs-lookup"><span data-stu-id="9584e-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="9584e-158">Definieren Sie als nächstes in [lync Server 2013 ein Gateway im Topologie-Generator](lync-server-2013-define-a-gateway-in-topology-builder.md) , und installieren Sie die Dateien auf jeder Vermittlungsserver im Pool, indem Sie die Verfahren unter [install the files for Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)ausführen.</span><span class="sxs-lookup"><span data-stu-id="9584e-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

