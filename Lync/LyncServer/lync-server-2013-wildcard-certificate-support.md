---
title: 'Lync Server 2013: Unterstützung von Platzhalterzertifikaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9422c3bebbb5fb32be88cfe5c41968207bbed2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="3c8ba-102">Unterstützung von Platzhalterzertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c8ba-103">_**Letztes Änderungsdatum des Themas:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="3c8ba-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="3c8ba-104">Lync Server 2013 verwendet Zertifikate, um Kommunikationsverschlüsselung und Authentifizierung von Server Identitäten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="3c8ba-105">In einigen Fällen, wie beispielsweise Web-Publishing über den Reverse-Proxy, ist ein starker Subject Alternative Name (San)-Eintrag, der dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers entspricht, der den Dienst darstellt, nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="3c8ba-106">In diesen Fällen können Sie Zertifikate mit Platzhalter-San-Einträgen (häufig als "Platzhalterzertifikate" bezeichnet) verwenden, um die Kosten für ein von einer öffentlichen Zertifizierungsstelle angefordertes Zertifikat zu verringern und die Komplexität des Planungsprozesses für Zertifikate zu verringern. .</span><span class="sxs-lookup"><span data-stu-id="3c8ba-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="3c8ba-107">Wenn Sie die Funktionalität von Unified Communications (UC)-Geräten (beispielsweise bei Tischtelefonen) beibehalten möchten, sollten Sie das bereitgestellte Zertifikat sorgfältig testen, um sicherzustellen, dass die Geräte ordnungsgemäß funktionieren, nachdem Sie ein Platzhalterzertifikat implementiert haben.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="3c8ba-108">Es gibt keine Unterstützung für einen Platzhaltereintrag als Antragstellernamen (auch als "allgemeiner Name" oder "CN" bezeichnet) für eine beliebige Rolle.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="3c8ba-109">Die folgenden Serverrollen werden bei Verwendung von Platzhaltereinträgen im San unterstützt:</span><span class="sxs-lookup"><span data-stu-id="3c8ba-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="3c8ba-110">**Reverseproxy**    Platzhalter-San-Eintrag wird für ein einfaches URL-Veröffentlichungs Zertifikat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="3c8ba-111">**Reverseproxy**    Platzhalter-San-Eintrag wird für die San-Einträge für LyncDiscover auf dem Veröffentlichungs Zertifikat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="3c8ba-112">**Director.**    Platzhalter-San-Eintrag wird für einfache URLs (Meet und Dialin) sowie für San-Einträge für LyncDiscover und LyncDiscoverInternal in Director Web Components unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="3c8ba-113">**Front-End-Server (Standard Edition) und Front-End-Pool (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="3c8ba-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="3c8ba-114">Platzhalter-San-Eintrag wird für einfache URLs (Meet und Dialin) sowie für San-Einträge für LyncDiscover und LyncDiscoverInternal in Front-End-Webkomponenten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="3c8ba-115">**Exchange Unified Messaging (um).**    Der Server verwendet keine San-Einträge, wenn er als eigenständiger Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="3c8ba-116">**Microsoft Exchange Server-Client Zugriffsserver**    Platzhaltereinträge im San werden für interne und externe Clients unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="3c8ba-117">**Exchange Unified Messaging (um) und Microsoft Exchange Server-Client Zugriffsserver auf demselben Server.**    Platzhalter-San-Einträge werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="3c8ba-118">Server Rollen, die in diesem Thema nicht behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="3c8ba-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="3c8ba-119">Interne Serverrollen (einschließlich, aber nicht nur auf den Vermittlungsserver, den Archivierungs-und Überwachungsserver, die Survivable Branch-Appliance oder den Survivable Branch-Server)</span><span class="sxs-lookup"><span data-stu-id="3c8ba-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="3c8ba-120">Externe Edgeserver-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3c8ba-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="3c8ba-121">Interner Edgeserver</span><span class="sxs-lookup"><span data-stu-id="3c8ba-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c8ba-122">Für die interne Edge-Server Schnittstelle kann dem San ein Platzhaltereintrag zugewiesen und unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="3c8ba-123">Das San auf dem internen Edgeserver wird nicht abgefragt, und ein Platzhalter-San-Eintrag hat einen geringen Wert.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="3c8ba-124">Details zu Zertifikat Konfigurationen, einschließlich der Verwendung von Platzhaltern in Zertifikaten, finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="3c8ba-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="3c8ba-125">Anforderungen an Zertifikate für interne Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="3c8ba-126">Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="3c8ba-127">Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="3c8ba-128">Zertifikatzusammenfassung für einen einzelnen Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="3c8ba-129">Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="3c8ba-130">Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="3c8ba-131">Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8ba-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="3c8ba-132">Details zum Konfigurieren von Zertifikaten für Exchange, einschließlich der Verwendung von Platzhaltern, finden Sie in der Exchange 2013-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3c8ba-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

