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
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="37b28-102">Konfigurieren von Netzwerkadaptern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37b28-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37b28-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="37b28-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="37b28-104">Sie müssen dem externen Netzwerkadapter eine oder mehrere IP-Adressen und mindestens eine IP-Adresse für den internen Netzwerkadapter zuweisen.</span><span class="sxs-lookup"><span data-stu-id="37b28-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="37b28-105">In den folgenden Verfahren verfügt der Server, auf dem Forefront Threat Management Gateway (TMG) 2010 oder Internet Information Server-Anwendungs Anforderungs Routing ausgeführt wird, über zwei Netzwerkadapter:</span><span class="sxs-lookup"><span data-stu-id="37b28-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="37b28-106">Ein öffentlicher oder externer Netzwerkadapter für Clients, die versuchen, eine Verbindung mit Ihrer Website herzustellen (in der Regel über das Internet).</span><span class="sxs-lookup"><span data-stu-id="37b28-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="37b28-107">Eine private oder interne Netzwerkschnittstelle für interne Server, auf denen lync Server ausgeführt wird, die Webdienste hosten.</span><span class="sxs-lookup"><span data-stu-id="37b28-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37b28-108">Ähnlich wie die Edgeserver setzen Sie das Standardgateway nur für den externen Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="37b28-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="37b28-109">Das Standardgateway ist die IP-Adresse des Routers oder der extern zugewandten Firewall, die den Datenverkehr an das Internet weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="37b28-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="37b28-110">Für Datenverkehr, der vom Reverse-Proxy an den internen Netzwerkadapter ausgerichtet ist, müssen Sie für alle Subnetze mit Servern, auf die die Webveröffentlichungsregeln verweisen, persistente statische Routen (wie den Befehl Route in Windows Server) verwenden.</span><span class="sxs-lookup"><span data-stu-id="37b28-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="37b28-111">Das Festlegen einer beständigen Route führt nicht dazu, dass der Computer zu einem Router wird.</span><span class="sxs-lookup"><span data-stu-id="37b28-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="37b28-112">Wenn die IP-Weiterleitung nicht aktiviert ist, handelt es sich bei dem Computer nur um den direkten bestimmten Datenverkehr, der für ein anderes Netzwerk bestimmt ist, an die entsprechende Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="37b28-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="37b28-113">Dies ist im Wesentlichen die Festlegung von zwei Gateways – einer als Standardverweis auf die externen Netzwerke und einer für den Datenverkehr, der an die interne Schnittstelle und an einen Router oder ein anderes Netzwerk weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="37b28-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="37b28-114">Das Erstellen beständiger Routen für alle Subnetze ist jedoch möglicherweise nicht erforderlich, wenn die Router Ihres Netzwerks für die Zusammenfassung von Routen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="37b28-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="37b28-115">Erstellen Sie eine permanente Route zu dem Netzwerk, in dem der Router definiert ist, und verwenden Sie den Router als Standardgateway.</span><span class="sxs-lookup"><span data-stu-id="37b28-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="37b28-116">Wenn Sie nicht genau wissen, wie Ihr Netzwerk konfiguriert ist und Anleitungen dazu benötigen, welche persistenten Routen erstellt werden müssen, konsultieren Sie die Netzwerktechniker Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="37b28-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="37b28-117">Der Reverseproxy muss in der Lage sein, die DNS-Hosteinträge (A) für den internen Director-oder Front-End-Server und die FQDNs des nächsten Hop zu beheben, die in den Webveröffentlichungsregeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37b28-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="37b28-118">Wie bei den Edge-Servern sollten Sie aus Sicherheitsgründen keinen Reverse-Proxy für die Verwendung eines DNS-Servers konfigurieren, der sich im internen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="37b28-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="37b28-119">Das bedeutet, dass Sie entweder DNS-Server im Umkreis benötigen, oder Sie benötigen Hosts-Dateieinträge auf dem Reverse-Proxy, der jede dieser FQDNs in die interne IP-Adresse der Server auflöst.</span><span class="sxs-lookup"><span data-stu-id="37b28-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="37b28-120">So konfigurieren Sie die Netzwerkadapterkarten auf dem Reverse Proxy-Computer</span><span class="sxs-lookup"><span data-stu-id="37b28-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="37b28-121">Öffnen Sie auf dem Windows Server 2008-, Windows Server 2008 R2-, Windows Server 2012-oder Windows Server 2012 R2-Server, der als Reverseproxy ausgeführt wird, die Option **Adaptereinstellungen ändern** , indem Sie auf **Start**klicken, auf **System**Steuerung zeigen, auf **Netzwerk-und Freigabe Center**klicken und dann auf **Adaptereinstellungen ändern**klicken.</span><span class="sxs-lookup"><span data-stu-id="37b28-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="37b28-122">Klicken Sie mit der rechten Maustaste auf die externe Netzwerkverbindung, die Sie für die externe Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="37b28-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="37b28-123">Klicken Sie auf der Seite **Eigenschaften** auf die Registerkarte **Netzwerk** , klicken Sie in der Liste **diese Verbindung verwendet die folgenden Elemente** auf **Internet Protokoll, Version 4 (TCP/IPv4)** , und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="37b28-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="37b28-124">Konfigurieren Sie auf der Seite **Eigenschaften von Internet Protokoll (TCP/IP)** die IP-Adressen entsprechend dem Netzwerk-Subnetz, an das der Netzwerkadapter angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="37b28-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37b28-125">Wenn der Reverse-Proxy bereits von anderen Anwendungen verwendet wird, die HTTPS/TCP/443 verwenden, wie bei der Veröffentlichung von Outlook Web Access müssen Sie entweder eine weitere IP-Adresse hinzufügen, damit Sie die lync Server 2013-Webdienste auf HTTPS/TCP/443 veröffentlichen können, ohne die vorhandenen Regeln und Weblistener zu stören, oder Sie müssen das vorhandene Zertifikat durch ein ersetzen, das dem alternativen Namen des Antragstellers den neuen Namen des externen FQDN hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="37b28-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="37b28-126">Klicken Sie auf **OK**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="37b28-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="37b28-127">Klicken Sie unter **Netzwerkverbindungen**mit der rechten Maustaste auf die interne Netzwerkverbindung, die Sie für die interne Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="37b28-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="37b28-128">Wiederholen Sie die Schritte 3 bis 5, um die interne Netzwerkverbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="37b28-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

