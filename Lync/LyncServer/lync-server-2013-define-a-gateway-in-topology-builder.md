---
title: 'Lync Server 2013: Definieren eines Gateways im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40881b38c83ebf254a60773060b642d183b7dfaa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="e65b7-102">Definieren eines Gateways im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e65b7-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e65b7-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="e65b7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="e65b7-104">Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen *Peer* zu definieren, dem Sie eine Vermittlungsserver zuordnen können, um eine Verbindung mit dem PSTN (Public Switched Telephone Network) für für Enterprise-VoIP aktivierte Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e65b7-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="e65b7-105">Ein Peer zum Vermittlungsserver kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein Session Border Controller (SBC) für einen Internet Telefonie-Dienstanbieter (ITSP) sein, zu dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e65b7-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e65b7-106">In diesem Thema wird davon ausgegangen, dass Sie mindestens einen internen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort mit einer nebeneinander liegenden oder eigenständigen Vermittlungsserver eingerichtet haben, wie in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren einer Front-End-Pool oder Standard Edition-Server in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e65b7-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="e65b7-107">In diesem Thema wird auch davon ausgegangen, dass Sie überprüft haben, dass Ihre Infrastruktur die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP in lync Server 2013</A> und <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013</A>beschriebenen Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="e65b7-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="e65b7-108">So definieren Sie einen Peer für den Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="e65b7-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="e65b7-109">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="e65b7-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e65b7-110">Klicken Sie unter lync Server 2013, Name Ihrer Website, freigegebene Komponenten mit der rechten Maustaste auf den Knoten **PSTN-Gateways** , und klicken Sie dann auf **Neues PSTN-Gateway**.</span><span class="sxs-lookup"><span data-stu-id="e65b7-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="e65b7-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="e65b7-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="e65b7-112">Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e65b7-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="e65b7-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="e65b7-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e65b7-114">Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsserver den FQDN angeben.</span><span class="sxs-lookup"><span data-stu-id="e65b7-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="e65b7-115">Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateway, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e65b7-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="e65b7-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="e65b7-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="e65b7-117">Definieren Sie einen *Stammtrunk* für das PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="e65b7-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="e65b7-118">Ein trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway, das durch das Tupel eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="e65b7-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="e65b7-119">{Vermittlungsserver FQDN, Vermittlungsserver Abhör Port (TLS oder TCP): Gateway-IP und FQDN, Gateway-Abhör Port}</span><span class="sxs-lookup"><span data-stu-id="e65b7-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="e65b7-120">Beim Definieren eines PSTN-Gateways im Topologie-Generator müssen Sie einen Stamm trunk definieren, um das PSTN-Gateway erfolgreich zu Ihrer Topologie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e65b7-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="e65b7-121">Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="e65b7-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="e65b7-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="e65b7-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="e65b7-123">Geben Sie unter **Überwachungsport für IP/PSTN-Gateway**den Abhör Port ein, den das Gateway, die Nebenstellenanlage oder der SBC für SIP-Nachrichten von der Vermittlungsserver verwendet, die dem Stamm trunk des PSTN-Gateways zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e65b7-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="e65b7-124">(In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e65b7-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="e65b7-125">Bei einem Survivable Branch Appliance an einem Zweigstellenstandort sind die Standardports 5081 für TCP und 5082 für TLS.)</span><span class="sxs-lookup"><span data-stu-id="e65b7-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="e65b7-126">Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e65b7-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e65b7-127">Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="e65b7-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="e65b7-128">Wählen Sie unter **zugeordnete Vermittlungsserver**den Vermittlungsserver Pool aus, der dem Stamm trunk dieses PSTN-Gateways zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e65b7-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="e65b7-129">Geben Sie unter **zugeordneter Vermittlungsserver Port**den Überwachungs Port ein, den der Vermittlungsserver für SIP-Nachrichten vom Gateway verwenden wird.</span><span class="sxs-lookup"><span data-stu-id="e65b7-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e65b7-130">Bei mehreren trunk Unterstützung in lync Server 2013 können mehrere SIP-Signalisierungs Ports für die Vermittlungsserver definiert werden, die für die Kommunikation mit mehreren PSTN-Gateways verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e65b7-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="e65b7-131">Beim Definieren eines Trunks muss sich der <STRONG>zugeordnete Vermittlungsserver Port</STRONG> innerhalb des Bereichs der Überwachungs Ports für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden.</span><span class="sxs-lookup"><span data-stu-id="e65b7-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="e65b7-132">Dieser Portbereich ist unter lync Server 2013 und Vermittlungs Pools definiert.</span><span class="sxs-lookup"><span data-stu-id="e65b7-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="e65b7-133">Klicken Sie mit der rechten Maustaste auf den Vermittlungsserver Interessen Pool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG>aus.</span><span class="sxs-lookup"><span data-stu-id="e65b7-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="e65b7-134">Geben Sie den Portbereich im Feld <STRONG>Überwachungsports</STRONG> ein.</span><span class="sxs-lookup"><span data-stu-id="e65b7-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="e65b7-135">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e65b7-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e65b7-136">Bevor Sie diesen Schritt abschließen, müssen Sie sicherstellen, dass der definierte Peer ausgeführt wird und den angegebenen FQDN bzw. die angegebene IP-Adresse verwendet.</span><span class="sxs-lookup"><span data-stu-id="e65b7-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="e65b7-137">Um den Peer zur Topologie hinzuzufügen, befolgen Sie die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e65b7-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="e65b7-138">Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um die Topologie zu erstellen oder zu ändern, damit die Daten für die Installation der Dateien für Server mit lync Server verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e65b7-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e65b7-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e65b7-139">See Also</span></span>


[<span data-ttu-id="e65b7-140">Ändern eines Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e65b7-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

