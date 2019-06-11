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

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Unterstützung von Platzhalterzertifikaten in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-21_

Lync Server 2013 verwendet Zertifikate, um Kommunikationsverschlüsselung und Authentifizierung von Server Identitäten bereitzustellen. In einigen Fällen, wie beispielsweise Web-Publishing über den Reverse-Proxy, ist ein starker Subject Alternative Name (San)-Eintrag, der dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers entspricht, der den Dienst darstellt, nicht erforderlich. In diesen Fällen können Sie Zertifikate mit Platzhalter-San-Einträgen (häufig als "Platzhalterzertifikate" bezeichnet) verwenden, um die Kosten für ein von einer öffentlichen Zertifizierungsstelle angefordertes Zertifikat zu verringern und die Komplexität des Planungsprozesses für Zertifikate zu verringern. .

<div>


> [!WARNING]  
> Wenn Sie die Funktionalität von Unified Communications (UC)-Geräten (beispielsweise bei Tischtelefonen) beibehalten möchten, sollten Sie das bereitgestellte Zertifikat sorgfältig testen, um sicherzustellen, dass die Geräte ordnungsgemäß funktionieren, nachdem Sie ein Platzhalterzertifikat implementiert haben.



</div>

Es gibt keine Unterstützung für einen Platzhaltereintrag als Antragstellernamen (auch als "allgemeiner Name" oder "CN" bezeichnet) für eine beliebige Rolle. Die folgenden Serverrollen werden bei Verwendung von Platzhaltereinträgen im San unterstützt:

  - <span></span>  
    **Reverseproxy**    Platzhalter-San-Eintrag wird für ein einfaches URL-Veröffentlichungs Zertifikat unterstützt.

  - <span></span>  
    **Reverseproxy**    Platzhalter-San-Eintrag wird für die San-Einträge für LyncDiscover auf dem Veröffentlichungs Zertifikat unterstützt.

  - <span></span>  
    **Director.**    Platzhalter-San-Eintrag wird für einfache URLs (Meet und Dialin) sowie für San-Einträge für LyncDiscover und LyncDiscoverInternal in Director Web Components unterstützt.

  - <span></span>  
    **Front-End-Server (Standard Edition) und Front-End-Pool (Enterprise Edition).** Platzhalter-San-Eintrag wird für einfache URLs (Meet und Dialin) sowie für San-Einträge für LyncDiscover und LyncDiscoverInternal in Front-End-Webkomponenten unterstützt.

  - <span></span>  
    **Exchange Unified Messaging (um).**    Der Server verwendet keine San-Einträge, wenn er als eigenständiger Server bereitgestellt wird.

  - <span></span>  
    **Microsoft Exchange Server-Client Zugriffsserver**    Platzhaltereinträge im San werden für interne und externe Clients unterstützt.

  - <span></span>  
    **Exchange Unified Messaging (um) und Microsoft Exchange Server-Client Zugriffsserver auf demselben Server.**    Platzhalter-San-Einträge werden unterstützt.

Server Rollen, die in diesem Thema nicht behandelt werden:

  - Interne Serverrollen (einschließlich, aber nicht nur auf den Vermittlungsserver, den Archivierungs-und Überwachungsserver, die Survivable Branch-Appliance oder den Survivable Branch-Server)

  - Externe Edgeserver-Schnittstellen

  - Interner Edgeserver
    
    <div>
    

    > [!NOTE]  
    > Für die interne Edge-Server Schnittstelle kann dem San ein Platzhaltereintrag zugewiesen und unterstützt werden. Das San auf dem internen Edgeserver wird nicht abgefragt, und ein Platzhalter-San-Eintrag hat einen geringen Wert.

    
    </div>

Details zu Zertifikat Konfigurationen, einschließlich der Verwendung von Platzhaltern in Zertifikaten, finden Sie unter den folgenden Themen:

  - [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Zertifikatzusammenfassung für einen einzelnen Director in Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Details zum Konfigurieren von Zertifikaten für Exchange, einschließlich der Verwendung von Platzhaltern, finden Sie in der Exchange 2013-Produktdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

