---
title: 'Lync Server 2013: Konfigurieren von Netzwerkadaptern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c114766bffb665e2c7da2850fefc6113365e4c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="ce548-102">Konfigurieren von Netzwerkadaptern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce548-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce548-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ce548-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ce548-104">Sie müssen der externen Netzwerkkarte eine oder mehrere IP-Adressen und der internen Netzwerkkarte mindestens eine IP-Adresse zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ce548-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="ce548-105">In den folgenden Verfahren verfügt der Server, auf dem Forefront Threat Management Gateway (TMG) 2010 oder Internet Information Server-Anwendungs Anforderungs Routing ausgeführt wird, über zwei Netzwerkadapter:</span><span class="sxs-lookup"><span data-stu-id="ce548-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="ce548-106">Eine öffentliche (oder externe) Netzwerkkarte für Clients, die versuchen, eine Verbindung zu Ihrer Website herzustellen (normalerweise über das Internet).</span><span class="sxs-lookup"><span data-stu-id="ce548-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="ce548-107">Eine private oder interne Netzwerkschnittstelle für interne Server, auf denen lync Server gehostet werden, die Webdienste hosten.</span><span class="sxs-lookup"><span data-stu-id="ce548-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce548-108">Ähnlich wie bei den Edgeserver legen Sie das Standardgateway nur für den externen Netzwerkadapter fest.</span><span class="sxs-lookup"><span data-stu-id="ce548-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="ce548-109">Das Standardgateway ist die IP-Adresse des Routers oder der Firewall mit externer Ausrichtung, die den Datenverkehr an das Internet weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="ce548-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="ce548-110">Für Datenverkehr, der vom Reverseproxy zum internen zugewandten Netzwerkadapter bestimmt ist, müssen Sie persistente statische Routen (wie den Befehl Route in Windows Server) für alle Subnetze mit Servern verwenden, auf die von den Webveröffentlichungsregeln verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ce548-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="ce548-111">Das Festlegen einer beständigen Route führt nicht dazu, dass der Computer zu einem Router wird.</span><span class="sxs-lookup"><span data-stu-id="ce548-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="ce548-112">Wenn die IP-Weiterleitung nicht aktiviert ist, handelt der Computer nur für den direkten spezifischen Datenverkehr, der für ein anderes Netzwerk bestimmt ist, an die entsprechende Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ce548-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="ce548-113">Im Wesentlichen werden zwei Gateways festgesetzt – eine als Standard, der auf die externen Netzwerke verweist, und eine für den Datenverkehr, der an die interne Schnittstelle und an einen Router oder ein anderes Netzwerk gerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ce548-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="ce548-p102">Wenn Ihr Router jedoch so konfiguriert ist, dass Routen zusammengefasst werden, brauchen Sie nicht für sämtliche Subnetze beständige Routen zu erstellen. Erstellen Sie eine beständige Route für das Netzwerk, in dem der Router definiert ist, und verwenden Sie den Router dann als Standardgateway. Wenn Sie nicht genau wissen, wie Ihr Netzwerk konfiguriert ist und genauere Anleitungen bezüglich der Erstellung von Routen benötigen, wenden Sie sich an die Netzwerkexperten Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="ce548-p102">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes. Create a persistent route to the network where the router is defined and use the router as the default gateway. If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="ce548-117">Der Reverseproxy muss in der Lage sein, die DNS-Hosteinträge (A) für die in den Webveröffentlichungsregeln verwendeten internen Director-oder Front-End-Server-und Next Hop-Pool-FQDN aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="ce548-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="ce548-118">Wie bei den Edgeserver empfiehlt es sich aus Sicherheitsgründen nicht, einen Reverseproxy für die Verwendung eines DNS-Servers im internen Netzwerk zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ce548-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="ce548-119">Das bedeutet, dass Sie entweder DNS-Server im Umkreisnetzwerk bereitstellen müssen oder HOST-Dateieinträge auf dem Reverseproxy benötigen, der die einzelnen FQDNs in die internen IP-Adressen der Server auflöst.</span><span class="sxs-lookup"><span data-stu-id="ce548-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="ce548-120">So konfigurieren Sie die Netzwerkkarten auf dem Reverseproxycomputer</span><span class="sxs-lookup"><span data-stu-id="ce548-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="ce548-121">Öffnen Sie auf dem Windows Server 2008-, Windows Server 2008 R2-, Windows Server 2012-oder Windows Server 2012 R2-Server, der als Reverseproxy angezeigt wird, **Adaptereinstellungen ändern** , indem Sie auf **Start**, auf **System**Steuerung, auf **Netzwerk-und Freigabe Center**und dann auf **Adapter Einstellungen ändern**klicken.</span><span class="sxs-lookup"><span data-stu-id="ce548-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="ce548-122">Klicken Sie mit der rechten Maustaste auf die externe Netzwerkverbindung, die Sie für die externe Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ce548-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="ce548-123">Klicken Sie auf der Seite **Eigenschaften** auf die Registerkarte **Netzwerk**, klicken Sie in der Liste **Diese Verbindung verwendet folgende Elemente** auf **Internetprotokoll Version 4 (TCP/IPv4)**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ce548-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="ce548-124">Konfigurieren Sie auf der Seite **Internetprotokolleigenschaften (TCP/IP)** die IP-Adressen entsprechend dem Netzwerksubnetz, an das die Netzwerkkarte angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ce548-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce548-125">Wenn der Reverseproxy bereits von anderen Anwendungen verwendet wird, die HTTPS/TCP/443 verwenden, beispielsweise zum Veröffentlichen von Outlook Web Access müssen Sie eine andere IP-Adresse hinzufügen, damit Sie die lync Server 2013 Webdienste auf HTTPS/TCP/443 veröffentlichen können, ohne die vorhandenen Regeln und die Weblistener zu stören, oder Sie müssen das vorhandene Zertifikat durch ein anderes ersetzen, das die neuen Namen des externen FQDN dem alternativen Antragstellernamen hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="ce548-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="ce548-126">Klicken Sie auf **OK** und dann nochmals auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce548-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ce548-127">Klicken Sie unter **Netzwerkverbindungen** mit der rechten Maustaste auf die interne Netzwerkverbindung, die Sie für die interne Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ce548-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="ce548-128">Wiederholen Sie die Schritte 3 bis 5, um die interne Netzwerkverbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ce548-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

