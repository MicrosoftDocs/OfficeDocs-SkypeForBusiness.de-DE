---
title: 'Lync Server 2013: Richtlinien für die Integration lokaler Unified Messaging-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15973bf2055339e375e4aecc7cfd1f61ac205dbb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="68def-102">Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68def-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68def-103">_**Letztes Änderungsdatum des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="68def-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="68def-104">Im Folgenden sind Richtlinien und bewährte Methoden aufgeführt, die Sie beim Bereitstellen von Enterprise-VoIP berücksichtigen sollten:</span><span class="sxs-lookup"><span data-stu-id="68def-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68def-105">Exchange Unified Messaging (um) unterstützt IPv6 nur, wenn Sie auch UCMA 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="68def-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="68def-106">Bereitstellen eines lync Server 2013 Standard Edition-Servers oder eines Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="68def-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="68def-107">Details zur Installation finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="68def-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="68def-108">Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="68def-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="68def-109">Stellen Sie die Exchange-Postfachserverrollen in jeder Exchange Unified Messaging (um)-Gesamtstruktur bereit, in der Sie die Benutzer für Exchange um aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="68def-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="68def-110">Ausführliche Informationen zum Installieren von Exchange-Serverrollen finden Sie in der Dokumentation zu Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68def-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="68def-111">Wenn Exchange Unified Messaging (um) installiert ist, ist es für die Verwendung eines selbstsignierten Zertifikats konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="68def-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="68def-112">Das selbstsignierte Zertifikat ermöglicht lync Server 2013 und Exchange um jedoch nicht, sich gegenseitig zu vertrauen, weshalb es notwendig ist, ein separates Zertifikat von einer Zertifizierungsstelle anzufordern, der beide Server Vertrauen.</span><span class="sxs-lookup"><span data-stu-id="68def-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="68def-113">Wenn lync Server 2013 und Exchange um in verschiedenen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013-Gesamtstruktur und der lync Server 2013-Gesamtstruktur vertrauen, um jeder Exchange-Gesamtstruktur zu vertrauen.</span><span class="sxs-lookup"><span data-stu-id="68def-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="68def-114">Darüber hinaus können Sie die Exchange um-Einstellungen der Benutzer für die Benutzerobjekte in der lync Server 2013-Gesamtstruktur festlegen, indem Sie in der Regel ein Skript oder ein Gesamtstrukturübergreifendes Tool verwenden, beispielsweise Identity Lifecycle Manager (ILM).</span><span class="sxs-lookup"><span data-stu-id="68def-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="68def-115">Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.</span><span class="sxs-lookup"><span data-stu-id="68def-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="68def-116">Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="68def-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="68def-117">Wenn Sie eine frühere Exchange-Version als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, koordinieren Sie die Namen für Exchange um SIP-URI-Wählpläne und Enterprise-VoIP-Wählpläne.</span><span class="sxs-lookup"><span data-stu-id="68def-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="68def-118">Bereitstellen redundanter Exchange UM-Server</span><span class="sxs-lookup"><span data-stu-id="68def-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68def-119">Wir empfehlen, dass Sie mindestens zwei Server bereitstellen, auf denen Exchange um-Dienste für jeden Exchange um-SIP-URI-Wählplan ausgeführt wird, den Sie für Ihre Organisation konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68def-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="68def-120">Zusätzlich zu einer höheren Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="68def-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="68def-121">Bei einem Serverfehler kann lync Server 2013 so konfiguriert werden, dass ein Failover zu einem anderen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68def-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="68def-122">Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="68def-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="68def-123">**Beispiel 1: Exchange UM-Ausfallsicherheit**</span><span class="sxs-lookup"><span data-stu-id="68def-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="68def-124">![Exchange um-Beispiel 1] (images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange um-Beispiel 1")</span><span class="sxs-lookup"><span data-stu-id="68def-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="68def-p105">In Beispiel 1 sind die Exchange UM-Server 1 und 2 im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Bei einem Exchange UM-Ausfall in Tukwila sollten die DNS-A-Einträge für die Server 1 und 2 so konfiguriert sein, dass sie auf den Server 3 bzw. 4 zeigen. Bei einem Exchange UM-Ausfall in Dublin sollten die DNS-A-Einträge für die Server 3 und 4 so konfiguriert sein, dass sie auf den Server 1 bzw. 2 zeigen.</span><span class="sxs-lookup"><span data-stu-id="68def-p105">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68def-128">In Beispiel 1 sollten Sie zudem auf jedem Exchange UM-Server eins der folgenden Zertifikate zuweisen:</span><span class="sxs-lookup"><span data-stu-id="68def-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="68def-129">Verwenden Sie ein Zertifikat mit einem Platzhalter im alternativen Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="68def-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="68def-130">Tragen Sie die vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der einzelnen Exchange UM-Server als alternativen Antragstellernamen ein.</span><span class="sxs-lookup"><span data-stu-id="68def-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="68def-131">**Beispiel 2: Exchange UM-Ausfallsicherheit**</span><span class="sxs-lookup"><span data-stu-id="68def-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="68def-132">![Exchange um-Beispiel 2] (images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange um-Beispiel 2")</span><span class="sxs-lookup"><span data-stu-id="68def-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="68def-p106">In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.</span><span class="sxs-lookup"><span data-stu-id="68def-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="68def-136">Details zum Aktivieren oder Deaktivieren von Unified Messaging auf Exchange 2013 finden Sie unter "Integration von Exchange 2013 um mit lync Server" unter [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span><span class="sxs-lookup"><span data-stu-id="68def-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="68def-137">Details zum Aktivieren oder Deaktivieren von Unified Messaging auf Microsoft Exchange Server 2010 finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="68def-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="68def-138">"Unified Messaging auf Exchange 2010 aktivieren" unter [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span><span class="sxs-lookup"><span data-stu-id="68def-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="68def-139">"Unified Messaging auf Exchange 2010 deaktivieren" unter [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span><span class="sxs-lookup"><span data-stu-id="68def-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68def-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68def-140">See Also</span></span>


[<span data-ttu-id="68def-141">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68def-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

