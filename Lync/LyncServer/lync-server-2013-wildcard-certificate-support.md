---
title: Unterstützung für lync Server 2013 Platzhalterzertifikat
description: Lync Server 2013 Unterstützung von Platzhalterzertifikaten.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46cc362eb925a86b5e90d51569db6d425ba88fa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546111"
---
# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="6e8f3-103">Unterstützung von Platzhalterzertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-103">Wildcard certificate support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e8f3-104">_**Letztes Änderungsstand des Themas:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="6e8f3-104">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="6e8f3-105">Lync Server 2013 verwendet Zertifikate zur Bereitstellung von Kommunikationsverschlüsselung und Server Identitätsauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-105">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="6e8f3-106">In manchen Fällen, z. B. bei Webveröffentlichung über den Reverseproxy, muss der Eintrag des alternativen Antragstellernamens (Subject Alternative Name, SAN) nicht genau mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers, der den Dienst anbietet, übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-106">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="6e8f3-107">In diesen Fällen können Sie Zertifikate mit Platzhalter-SAN-Einträgen (so genannte "Platzhalterzertifikate") verwenden, um die Kosten eines Zertifikats von einer öffentlichen Zertifizierungsstelle und die Komplexität der Planung für Zertifikate zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-107">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6e8f3-108">Um die Funktionalität von Unified Communications-Geräten (UC) wie z. B. Tischtelefonen aufrechtzuerhalten, sollten Sie das bereitgestellte Zertifikat sorgfältig testen, um sicherzustellen, dass die Geräte nach der Implementierung eines Platzhalterzertifikats ordnungsgemäß funktionsfähig sind.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-108">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="6e8f3-p102">Ein Platzhaltereintrag als Antragstellername (auch als "allgemeiner Name" (Common Name, CN) bezeichnet) wird für keine Rolle unterstützt. Für die folgenden Serverrollen wird die Verwendung von Platzhaltereinträgen im SAN unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6e8f3-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="6e8f3-111">**Reverseproxy.**     Platzhalter-San-Eintrag wird für das Veröffentlichungs Zertifikat für einfache URLs (Meet and Dialin) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-111">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="6e8f3-112">**Reverseproxy.**     Platzhalter-San-Eintrag wird für die San-Einträge für LyncDiscover im Veröffentlichungs Zertifikat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-112">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="6e8f3-113">**Director.**     Platzhalter-San-Eintrag wird für einfache URLs (Meet and Dialin) und für San-Einträge für LyncDiscover und "lyncdiscoverinternal" in Director-Webkomponenten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-113">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="6e8f3-114">**Front-End-Server (Standard Edition) und Front-End-Pool (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="6e8f3-114">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="6e8f3-115">Platzhalter-San-Eintrag wird für einfache URLs (Meet and Dialin) und für San-Einträge für LyncDiscover und "lyncdiscoverinternal" in Front-End-Webkomponenten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-115">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="6e8f3-116">**Exchange Unified Messaging (um).**     Der Server verwendet keine San-Einträge, wenn er als eigenständiger Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-116">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="6e8f3-117">**Exchange Server Client Zugriffs Server.**     Platzhaltereinträge im San werden für interne und externe Clients unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-117">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="6e8f3-118">**Exchange Unified Messaging (um) und Exchange Server Client Zugriffsserver auf demselben Server.**     Platzhalter-San-Einträge werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-118">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="6e8f3-119">In diesem Thema nicht behandelte Serverrollen:</span><span class="sxs-lookup"><span data-stu-id="6e8f3-119">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="6e8f3-120">Interne Serverrollen (einschließlich, aber nicht ausschließlich für die Vermittlungsserver, Archivierungs-und Monitoring Server, Survivable Branch Appliance oder Survivable Branch Server)</span><span class="sxs-lookup"><span data-stu-id="6e8f3-120">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="6e8f3-121">Externe Edgeserver-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6e8f3-121">External Edge Server interfaces</span></span>

  - <span data-ttu-id="6e8f3-122">Interne Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6e8f3-122">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e8f3-123">Für die interne Edgeserver-Schnittstelle kann dem San ein Platzhaltereintrag zugewiesen werden und wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-123">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="6e8f3-124">Das San im internen Edgeserver wird nicht abgefragt, und ein Platzhalter-San-Eintrag hat einen begrenzten Wert.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-124">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="6e8f3-125">Ausführliche Informationen zu Zertifikat Konfigurationen, einschließlich der Verwendung von Platzhalterzeichen in Zertifikaten, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6e8f3-125">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="6e8f3-126">Zertifikatanforderungen für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-126">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="6e8f3-127">Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-127">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="6e8f3-128">Zertifikatzusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-128">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="6e8f3-129">Zertifikatzusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-129">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="6e8f3-130">Zertifikatzusammenfassung für skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-130">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="6e8f3-131">Zertifikatzusammenfassung-Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-131">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="6e8f3-132">Richtlinien für die Integration von lokalen Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f3-132">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="6e8f3-133">Ausführliche Informationen zum Konfigurieren von Zertifikaten für Exchange, einschließlich der Verwendung von Platzhaltern, finden Sie in der Exchange 2013-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6e8f3-133">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

