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
# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Unterstützung von Platzhalterzertifikaten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-21_

Lync Server 2013 verwendet Zertifikate zur Bereitstellung von Kommunikationsverschlüsselung und Server Identitätsauthentifizierung. In manchen Fällen, z. B. bei Webveröffentlichung über den Reverseproxy, muss der Eintrag des alternativen Antragstellernamens (Subject Alternative Name, SAN) nicht genau mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers, der den Dienst anbietet, übereinstimmen. In diesen Fällen können Sie Zertifikate mit Platzhalter-SAN-Einträgen (so genannte "Platzhalterzertifikate") verwenden, um die Kosten eines Zertifikats von einer öffentlichen Zertifizierungsstelle und die Komplexität der Planung für Zertifikate zu reduzieren.

<div>


> [!WARNING]  
> Um die Funktionalität von Unified Communications-Geräten (UC) wie z. B. Tischtelefonen aufrechtzuerhalten, sollten Sie das bereitgestellte Zertifikat sorgfältig testen, um sicherzustellen, dass die Geräte nach der Implementierung eines Platzhalterzertifikats ordnungsgemäß funktionsfähig sind.



</div>

Ein Platzhaltereintrag als Antragstellername (auch als "allgemeiner Name" (Common Name, CN) bezeichnet) wird für keine Rolle unterstützt. Für die folgenden Serverrollen wird die Verwendung von Platzhaltereinträgen im SAN unterstützt:

  - <span></span>  
    **Reverseproxy.**     Platzhalter-San-Eintrag wird für das Veröffentlichungs Zertifikat für einfache URLs (Meet and Dialin) unterstützt.

  - <span></span>  
    **Reverseproxy.**     Platzhalter-San-Eintrag wird für die San-Einträge für LyncDiscover im Veröffentlichungs Zertifikat unterstützt.

  - <span></span>  
    **Director.**     Platzhalter-San-Eintrag wird für einfache URLs (Meet and Dialin) und für San-Einträge für LyncDiscover und "lyncdiscoverinternal" in Director-Webkomponenten unterstützt.

  - <span></span>  
    **Front-End-Server (Standard Edition) und Front-End-Pool (Enterprise Edition).** Platzhalter-San-Eintrag wird für einfache URLs (Meet and Dialin) und für San-Einträge für LyncDiscover und "lyncdiscoverinternal" in Front-End-Webkomponenten unterstützt.

  - <span></span>  
    **Exchange Unified Messaging (um).**     Der Server verwendet keine San-Einträge, wenn er als eigenständiger Server bereitgestellt wird.

  - <span></span>  
    **Exchange Server Client Zugriffs Server.**     Platzhaltereinträge im San werden für interne und externe Clients unterstützt.

  - <span></span>  
    **Exchange Unified Messaging (um) und Exchange Server Client Zugriffsserver auf demselben Server.**     Platzhalter-San-Einträge werden unterstützt.

In diesem Thema nicht behandelte Serverrollen:

  - Interne Serverrollen (einschließlich, aber nicht ausschließlich für die Vermittlungsserver, Archivierungs-und Monitoring Server, Survivable Branch Appliance oder Survivable Branch Server)

  - Externe Edgeserver-Schnittstellen

  - Interne Edgeserver
    
    <div>
    

    > [!NOTE]  
    > Für die interne Edgeserver-Schnittstelle kann dem San ein Platzhaltereintrag zugewiesen werden und wird unterstützt. Das San im internen Edgeserver wird nicht abgefragt, und ein Platzhalter-San-Eintrag hat einen begrenzten Wert.

    
    </div>

Ausführliche Informationen zu Zertifikat Konfigurationen, einschließlich der Verwendung von Platzhalterzeichen in Zertifikaten, finden Sie in den folgenden Themen:

  - [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Zertifikatzusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Zertifikatzusammenfassung für einen einzelnen Director in lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Zertifikatzusammenfassung für skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Zertifikatzusammenfassung-Reverseproxy in lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Richtlinien für die Integration von lokalen Unified Messaging-und lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Ausführliche Informationen zum Konfigurieren von Zertifikaten für Exchange, einschließlich der Verwendung von Platzhaltern, finden Sie in der Exchange 2013-Produktdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

