---
title: 'Lync Server 2013: Einrichten von Netzwerkschnittstellen für Edgeserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 267db7062c19a0b1344d11f27205a51bf1e750ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="470c5-102">Einrichten von Netzwerkschnittstellen für Edgeserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="470c5-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="470c5-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="470c5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="470c5-104">Jeder Edgeserver ist ein mehrfach vernetzter Computer mit externen und internen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="470c5-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="470c5-105">Die Einstellungen für den Adapter Domain Name System (DNS) hängen davon ab, ob sich DNS-Server im Umkreisnetzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="470c5-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="470c5-106">Wenn sich DNS-Server im Umkreis befinden, müssen Sie über eine Zone mit mindestens einem DNS-a-Eintrag für den nächsten Hop-Server oder-Pool verfügen (also entweder Director oder Designated Front-End-Pool), und für externe Abfragen, die Sie Namenssuche auf andere öffentliche DNS-Server referieren.</span><span class="sxs-lookup"><span data-stu-id="470c5-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="470c5-107">Wenn im Umkreis keine DNS-Server vorhanden sind, verwenden die Edgeserver (s) externe DNS-Server zum Auflösen von Internet Namen suchen, und jede Edgeserver verwendet einen Host, um die Server Namen des nächsten Hops in IP-Adressen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="470c5-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="470c5-109">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="470c5-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="470c5-110">Aus Sicherheitsgründen wird empfohlen, dass Ihre Edgeserver nicht auf einen DNS-Server zugreifen können, der sich im internen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="470c5-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="470c5-111">So konfigurieren Sie Schnittstellen mit DNS-Servern im Umkreisnetzwerk</span><span class="sxs-lookup"><span data-stu-id="470c5-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="470c5-112">Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern ausgerichtete Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="470c5-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="470c5-113">Die internen und externen Subnetze dürfen nicht zueinander geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="470c5-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="470c5-114">Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks (auch als DMZ, demilitarisierte Zone und überwachtes Subnetz bezeichnet), und richten Sie das Standardgateway auf die interne Schnittstelle der externen Firewall.</span><span class="sxs-lookup"><span data-stu-id="470c5-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="470c5-115">Konfigurieren Sie die DNS-Einstellungen des Adapters so, dass Sie auf ein paar von Umkreis-DNS-Servern deuten.</span><span class="sxs-lookup"><span data-stu-id="470c5-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="470c5-116">Für diese Schnittstelle ist es möglich, nur eine IP-Adresse zu verwenden, aber dazu müssen Sie die Portzuweisungen in nicht-Standardwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="470c5-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="470c5-117">Sie bestimmen dies, wenn Sie die Topologie im Topologie-Generator erstellen.</span><span class="sxs-lookup"><span data-stu-id="470c5-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="470c5-118">Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway fest.</span><span class="sxs-lookup"><span data-stu-id="470c5-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="470c5-119">Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass Sie auf mindestens einen DNS-Server, vorzugsweise ein paar von Umkreis-DNS-Servern, verweist.</span><span class="sxs-lookup"><span data-stu-id="470c5-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="470c5-120">Erstellen Sie persistente statische Routen auf der internen Schnittstelle zu allen internen Netzwerken, in denen sich Clients, lync Server 2013 und Exchange Unified Messaging (um) Server befinden.</span><span class="sxs-lookup"><span data-stu-id="470c5-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="470c5-121">So konfigurieren Sie Schnittstellen ohne DNS-Server im Umkreisnetzwerk</span><span class="sxs-lookup"><span data-stu-id="470c5-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="470c5-122">Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern ausgerichtete Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="470c5-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="470c5-123">Die internen und externen Subnetze dürfen nicht zueinander geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="470c5-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="470c5-124">Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="470c5-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="470c5-125">Außerdem konfigurieren Sie das Standardgateway für die externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="470c5-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="470c5-126">Definieren Sie beispielsweise den mit dem Internet verbundenen Router oder die externe Firewall als Standardgateway.</span><span class="sxs-lookup"><span data-stu-id="470c5-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="470c5-127">Konfigurieren Sie DNS-Einstellungen so, dass Sie auf einen DNS-Server, vorzugsweise auf ein paar externer DNS-Server, verweist.</span><span class="sxs-lookup"><span data-stu-id="470c5-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="470c5-128">Es ist möglich, aber nicht empfehlenswert, nur so wenige IP-Adressen für die externe Schnittstelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="470c5-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="470c5-129">Damit dies funktioniert, müssen Sie die Portzuweisungen auf nicht standardmäßige Werte und den standardmäßigen Port 443, der normalerweise "Firewall-freundlich" für die Clientkommunikation ist, ändern.</span><span class="sxs-lookup"><span data-stu-id="470c5-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="470c5-130">Sie bestimmen die IP-Adresseinstellung und die Porteinstellungen beim Erstellen der Topologie im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="470c5-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="470c5-131">Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway fest.</span><span class="sxs-lookup"><span data-stu-id="470c5-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="470c5-132">Lassen Sie die Adapter-DNS-Einstellungen leer.</span><span class="sxs-lookup"><span data-stu-id="470c5-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="470c5-133">Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, in denen sich lync-Clients oder-Server mit lync Server 2013 befinden.</span><span class="sxs-lookup"><span data-stu-id="470c5-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="470c5-134">Bearbeiten Sie die Hostdatei auf jeder Edgeserver, um einen Datensatz für den nächsten Hop-Server oder die virtuelle IP (VIP) aufzunehmen (der Datensatz ist der Director, Standard Edition-Server oder ein Front-End-Pool, der als Edgeserver nächster Hop-Adresse im Topologie-Generator konfiguriert wurde).</span><span class="sxs-lookup"><span data-stu-id="470c5-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="470c5-135">Wenn Sie DNS-Lastenausgleich verwenden, fügen Sie für jedes Mitglied des Pools für den nächsten Hop eine Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="470c5-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

