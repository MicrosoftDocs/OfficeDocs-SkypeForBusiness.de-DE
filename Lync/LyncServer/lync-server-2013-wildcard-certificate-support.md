---
title: 'Lync Server 2013: Unterstützung von Platzhalterzertifikaten'
TOCTitle: Unterstützung von Platzhalterzertifikaten
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202161(v=OCS.15)
ms:contentKeyID: 49293144
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung von Platzhalterzertifikaten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-21_

In Lync Server 2013 werden Zertifikate für die Verschlüsselung der Kommunikation und die Authentifizierung der Serveridentität verwendet. In manchen Fällen, z. B. bei Webveröffentlichung über den Reverseproxy, muss der Eintrag des alternativen Antragstellernamens (Subject Alternative Name, SAN) nicht genau mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers, der den Dienst anbietet, übereinstimmen. In diesen Fällen können Sie Zertifikate mit Platzhalter-SAN-Einträgen (so genannte "Platzhalterzertifikate") verwenden, um die Kosten eines Zertifikats von einer öffentlichen Zertifizierungsstelle und die Komplexität der Planung für Zertifikate zu reduzieren.


> [!WARNING]
> Um die Funktionalität von Unified Communications-Geräten (UC) wie z.&nbsp;B. Tischtelefonen aufrechtzuerhalten, sollten Sie das bereitgestellte Zertifikat sorgfältig testen, um sicherzustellen, dass die Geräte nach der Implementierung eines Platzhalterzertifikats ordnungsgemäß funktionsfähig sind.



Ein Platzhaltereintrag als Antragstellername (auch als "allgemeiner Name" (Common Name, CN) bezeichnet) wird für keine Rolle unterstützt. Für die folgenden Serverrollen wird die Verwendung von Platzhaltereinträgen im SAN unterstützt:

  - **Reverseproxy.**   Platzhalter-SAN-Eintrag wird für Herausgeberzertifikat mit einfacher URL (Besprechung/meet und Wählen/dialin) unterstützt.

  - **Reverseproxy.**   Platzhalter-SAN-Eintrag wird für die SAN-Einträge für LyncDiscover im Herausgeberzertifikat unterstützt.

  - **Director.** Platzhalter-SAN-Eintrag wird für einfache URLs (Besprechung/meet und Wählen/dialin) sowie für SAN-Einträge für LyncDiscover und LyncDiscoverInternal in Directorwebkomponenten unterstützt.

  - **Front-End-Server ( Standard Edition) und Front-End-Pool ( Enterprise Edition).** Platzhalter-SAN-Eintrag wird für einfache URLs (Besprechung/meet und Wählen/dialin) sowie für SAN-Einträge für LyncDiscover und LyncDiscoverInternal in Front-End-Webkomponenten unterstützt.

  - **Exchange Unified Messaging (UM).** Der Server verwendet keine SAN-Einträge, wenn er als eigenständiger Server bereitgestellt wurde.

  - **Microsoft Exchange Server Clientzugriffsserver.** Platzhaltereinträge im SAN werden für interne und externe Clients unterstützt.

  - **Exchange Unified Messaging (UM) und Microsoft Exchange Server Clientzugriffsserver auf demselben Server.** Platzhalter-SAN-Einträge werden unterstützt.

In diesem Thema nicht behandelte Serverrollen:

  - Interne Serverrollen (u. a. Vermittlungsserver, Archivierungs- und Monitoring Server, Survivable Branch-Anwendung oder Survivable Branch-Server)

  - Externe Edgeserver-Schnittstellen

  - Interner Edgeserver
    

    > [!NOTE]
    > Für die interne Edgeserver-Schnittstelle kann dem SAN ein Platzhaltereintrag zugewiesen werden und wird unterstützt. Der SAN für den internen Edgeserver wird nicht abgefragt. Ein Platzhalter-SAN-Eintrag ist somit wertlos.



Ausführliche Informationen zu Zertifikatkonfigurationen, darunter zur Verwendung von Platzhaltern in Zertifikaten finden Sie in den folgenden Themen:

  - [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Zertifikatzusammenfassung für einen einzelnen Director in Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Ausführliche Informationen zum Konfigurieren von Zertifikaten für Exchange, darunter zur Verwendung von Platzhaltern finden Sie in der Exchange 2013-Produktdokumentation.

