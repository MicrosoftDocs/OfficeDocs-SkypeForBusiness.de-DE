---
title: 'Lync Server 2013: Definieren zusätzlicher Trunks im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5632a5f28a5a56d077235e28be41c19b5496c10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="99de6-102">Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99de6-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99de6-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="99de6-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="99de6-104">Führen Sie die folgenden Schritte aus, um den Topologie-Generator zum Definieren eines zusätzlichen Trunks zu verwenden, dem Sie einen *Peer* einem Vermittlungsserver zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="99de6-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="99de6-105">Ein Peer stellt für Enterprise-VoIP aktivierte Benutzer Verbindungen mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN) bereit.</span><span class="sxs-lookup"><span data-stu-id="99de6-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="99de6-106">Bei dem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.</span><span class="sxs-lookup"><span data-stu-id="99de6-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="99de6-107">Der trunk definiert diese Verbindung zwischen dem Vermittlungsserver und dem Peer.</span><span class="sxs-lookup"><span data-stu-id="99de6-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="99de6-108">Pro Vermittlungsserver können mehrere Trunks definiert werden.</span><span class="sxs-lookup"><span data-stu-id="99de6-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="99de6-109">Ein Vermittlungsserver kann mehreren Peers zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="99de6-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="99de6-110">Ein trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway, das durch das Tupel eindeutig identifiziert wird:</span><span class="sxs-lookup"><span data-stu-id="99de6-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="99de6-111">{Vermittlungsserver FQDN, Vermittlungsserver Abhör Port (TLS oder TCP): Gateway-IP und FQDN, Gateway-Abhör Port}</span><span class="sxs-lookup"><span data-stu-id="99de6-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99de6-112">In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stamm trunk mit mindestens einem verbundenen oder eigenständigen Vermittlungsserver oder Pool eingerichtet haben, wie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a Gateway in Topology Builder in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99de6-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="99de6-113">In diesem Thema wird davon ausgegangen, dass Sie mindestens einen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99de6-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="99de6-114">So definieren Sie einen zusätzlichen trunk zwischen einem Vermittlungsserver und einem Gateway-Peer</span><span class="sxs-lookup"><span data-stu-id="99de6-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="99de6-115">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="99de6-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="99de6-116">Klicken Sie unter lync Server 2013, Name Ihrer Website, **freigegebene Komponenten**mit der rechten Maustaste auf den Knoten **Trunks** , und klicken Sie dann auf **neuer trunk**.</span><span class="sxs-lookup"><span data-stu-id="99de6-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="99de6-117">![Dateistruktur Bildschirm für lync Server Topologie-Generator](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Dateistruktur Bildschirm für lync Server Topologie-Generator")</span><span class="sxs-lookup"><span data-stu-id="99de6-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="99de6-118">Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="99de6-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="99de6-119">Zwei Trunks mit demselben Namen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="99de6-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99de6-120">Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsserver den FQDN angeben.</span><span class="sxs-lookup"><span data-stu-id="99de6-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="99de6-121">Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="99de6-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="99de6-122">![Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk")</span><span class="sxs-lookup"><span data-stu-id="99de6-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="99de6-123">Geben Sie unter **Abhör Port für PSTN-Gateway**den Abhör Port ein, den der Peer (PSTN-Gateway, IP-PBX oder SBC) SIP-Nachrichten von dem Vermittlungsserver empfängt, der diesem trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="99de6-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="99de6-124">Die standardmäßigen Peer Ports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="99de6-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="99de6-125">Die Standard Survivable Branch Appliance Ports sind 5081 für TCP und 5082 für TLS.</span><span class="sxs-lookup"><span data-stu-id="99de6-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="99de6-126">Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.</span><span class="sxs-lookup"><span data-stu-id="99de6-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99de6-127">Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="99de6-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="99de6-128">Wählen Sie unter **zugeordnete Vermittlungsserver**den Vermittlungsserver-Pool aus, der dem Stamm trunk dieses Peers zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="99de6-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="99de6-129">Geben Sie unter **zugeordneter Vermittlungsserver Port**den Abhör Port ein, über den der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.</span><span class="sxs-lookup"><span data-stu-id="99de6-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99de6-130">Bei mehreren trunk-Unterstützung in lync Server 2013 können zwei Trunks mit unterschiedlichen trunk Namen nicht mit dem gleichen <STRONG>zugeordneten Vermittlungsserver-Port</STRONG> und dem <STRONG>Überwachungs Port für IP/PSTN-Gateway</STRONG> konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="99de6-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99de6-131">Bei mehreren trunk Unterstützung in lync Server 2013 können mehrere SIP-Signalisierungs Ports für die Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden.</span><span class="sxs-lookup"><span data-stu-id="99de6-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="99de6-132">Beim Definieren eines Trunks muss sich die <STRONG>zugeordnete Vermittlungsserver Port</STRONG> Nummer innerhalb des Bereichs der Überwachungs Ports für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden.</span><span class="sxs-lookup"><span data-stu-id="99de6-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="99de6-133">Dieser Portbereich ist unter lync Server 2013-und Vermittlungsserver-Pools definiert.</span><span class="sxs-lookup"><span data-stu-id="99de6-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="99de6-134">Klicken Sie mit der rechten Maustaste auf den betreffenden Vermittlungsserver Pool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG>aus.</span><span class="sxs-lookup"><span data-stu-id="99de6-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="99de6-135">Geben Sie den Portbereich im Feld <STRONG>Überwachungsports</STRONG> an.</span><span class="sxs-lookup"><span data-stu-id="99de6-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="99de6-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99de6-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99de6-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99de6-137">See Also</span></span>


[<span data-ttu-id="99de6-138">Ändern eines Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99de6-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

