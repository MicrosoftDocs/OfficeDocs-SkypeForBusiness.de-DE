---
title: 'Lync Server 2013: Richtlinien für die Integration von lokalen Unified Messaging-Funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be763250edf7222b900aef88665b3e360e8125c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="9c507-102">Richtlinien für die Integration von lokalen Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c507-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c507-103">_**Letztes Änderungsstand des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="9c507-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="9c507-104">Im folgenden sind Richtlinien und bewährte Methoden für die Bereitstellung von Enterprise-VoIP zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="9c507-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9c507-105">Exchange Unified Messaging (um) unterstützt IPv6 nur, wenn Sie auch UCMA 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c507-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="9c507-106">Bereitstelleneiner lync Server 2013 Standard Edition-Server oder eines Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="9c507-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="9c507-107">Ausführliche Informationen zur Installation finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9c507-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="9c507-108">Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="9c507-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="9c507-109">Stellen Sie die Exchange-Postfachserverrollen in jeder Exchange Unified Messaging (um) Gesamtstruktur bereit, in der Sie Benutzer für Exchange um aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9c507-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="9c507-110">Ausführliche Informationen zum Installieren von Exchange-Serverrollen finden Sie in der Microsoft Exchange Server 2013 Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9c507-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9c507-111">Wenn Exchange Unified Messaging (um) installiert ist, ist es für die Verwendung eines selbstsignierten Zertifikats konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9c507-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="9c507-112">Das selbstsignierte Zertifikat ermöglicht jedoch nicht, dass lync Server 2013 und Exchange um einander vertrauen, weshalb es erforderlich ist, ein separates Zertifikat von einer Zertifizierungsstelle anzufordern, der beide Server Vertrauen.</span><span class="sxs-lookup"><span data-stu-id="9c507-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="9c507-113">Wenn lync Server 2013 und Exchange um in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013 Gesamtstruktur und der lync Server 2013 Gesamtstruktur als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="9c507-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="9c507-114">Legen Sie außerdem die Exchange um Einstellungen der Benutzer für die Benutzerobjekte in der lync Server 2013 Gesamtstruktur fest, in der Regel mithilfe eines Skripts oder eines gesamtstrukturübergreifenden Tools wie Identity Lifecycle Manager (ILM).</span><span class="sxs-lookup"><span data-stu-id="9c507-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="9c507-115">Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.</span><span class="sxs-lookup"><span data-stu-id="9c507-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="9c507-116">Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="9c507-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="9c507-117">Wenn Sie eine Version von Exchange um früher als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, koordinieren Sie die Namen für Exchange um SIP-URI-Wählpläne und Enterprise-VoIP-Wähl Pläne.</span><span class="sxs-lookup"><span data-stu-id="9c507-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="9c507-118">Bereitstellen redundanter Exchange UM-Server</span><span class="sxs-lookup"><span data-stu-id="9c507-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9c507-119">Es wird empfohlen, mindestens zwei Server bereitzustellen, auf denen Exchange um Dienste für alle Exchange um SIP-URI-Wähleinstellungen, die Sie für Ihre Organisation konfigurieren, durchführen.</span><span class="sxs-lookup"><span data-stu-id="9c507-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="9c507-120">Neben der erweiterten Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="9c507-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="9c507-121">Bei einem Serverausfall können lync Server 2013 so konfiguriert werden, dass ein Failover auf einen anderen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9c507-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="9c507-122">Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="9c507-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="9c507-123">**Beispiel 1: Exchange UM-Ausfallsicherheit**</span><span class="sxs-lookup"><span data-stu-id="9c507-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="9c507-124">![Exchange um Beispiel 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange um Beispiel 1")</span><span class="sxs-lookup"><span data-stu-id="9c507-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="9c507-125">In Beispiel 1 sind Exchange um Server 1 und 2 im Rechenzentrum von Tukwila aktiviert, und Exchange um Server 3 und 4 sind im Dublin-Rechenzentrum aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9c507-125">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="9c507-126">Bei einem Exchange um Ausfall in Tukwila sollte die Domain Name System (DNS) A-Einträge für Server 1 und 2 so konfiguriert werden, dass Sie auf Server 3 und 4 verweist.</span><span class="sxs-lookup"><span data-stu-id="9c507-126">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="9c507-127">Bei einem Exchange um Ausfall in Dublin sollten die DNS-A-Einträge für Server 3 und 4 so konfiguriert werden, dass Sie auf Server 1 und 2 verweist.</span><span class="sxs-lookup"><span data-stu-id="9c507-127">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c507-128">In Beispiel 1 sollten Sie zudem auf jedem Exchange UM-Server eins der folgenden Zertifikate zuweisen:</span><span class="sxs-lookup"><span data-stu-id="9c507-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9c507-129">Verwenden Sie ein Zertifikat mit einem Platzhalter im alternativen Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="9c507-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="9c507-130">Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der vier Exchange um Server im San ein.</span><span class="sxs-lookup"><span data-stu-id="9c507-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="9c507-131">**Beispiel 2: Exchange UM-Ausfallsicherheit**</span><span class="sxs-lookup"><span data-stu-id="9c507-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="9c507-132">![Exchange um Beispiel 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange um Beispiel 2")</span><span class="sxs-lookup"><span data-stu-id="9c507-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="9c507-p106">In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.</span><span class="sxs-lookup"><span data-stu-id="9c507-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="9c507-136">Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging für Exchange 2013 finden Sie unter "integrieren Exchange 2013 um mit lync Server" unter [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span><span class="sxs-lookup"><span data-stu-id="9c507-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="9c507-137">Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging für Microsoft Exchange Server 2010 finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="9c507-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="9c507-138">"Aktivieren von Unified Messaging bei Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)unter.</span><span class="sxs-lookup"><span data-stu-id="9c507-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="9c507-139">"Deaktivieren von Unified Messaging auf Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)unter.</span><span class="sxs-lookup"><span data-stu-id="9c507-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c507-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c507-140">See Also</span></span>


[<span data-ttu-id="9c507-141">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c507-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

