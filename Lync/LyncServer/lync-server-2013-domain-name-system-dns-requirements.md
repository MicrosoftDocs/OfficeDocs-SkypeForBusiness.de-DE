---
title: DNS-Anforderungen (Domain Name System)
TOCTitle: DNS-Anforderungen (Domain Name System)
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398386(v=OCS.15)
ms:contentKeyID: 49294069
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen (Domain Name System)

 

_**Letztes Änderungsdatum des Themas:** 2012-06-18_

Für die Bereitstellung von Lync Server müssen Sie DNS-Einträge (Domain Name System) erstellen, die die Ermittlung von Clients und Servern ermöglichen und (optional) die automatische Clientanmeldung unterstützen, sofern diese in Ihrer Organisation gewünscht ist.

Lync Server verwendet DNS für folgende Zwecke:

  - Zum Erkennen interner Server oder Pools für die Kommunikation zwischen Servern.

  - Damit Clients den Front-End-Pool oder den Standard Edition-Server erkennen können, der für verschiedene SIP-Transaktionen verwendet wird.

  - Damit nicht angemeldete UC-Geräte (Unified Communications) den Front-End-Pool oder den Standard Edition-Server ermitteln können, auf dem der Geräteaktualisierungswebdienst ausgeführt wird, sowie Updates abrufen und Protokolle senden können.

  - Damit externe Server und Clients für Sofortnachrichten oder für Konferenzen eine Verbindung mit dem Edgeserver oder dem HTTP-Reverseproxy herstellen können.

  - Damit externe UC-Geräte über Edgeserver oder den HTTP-Reverseproxy eine Verbindung mit dem Geräteaktualisierungswebdienst herstellen und Updates abrufen können.

  - Damit mobile Clients automatisch Webdienstressourcen ermitteln können, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.

## In diesem Abschnitt

  - [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [DNS-Anforderungen für Front-End-Pools](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [DNS-Anforderungen für Standard Edition-Server](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [DNS-Anforderungen für die automatische Clientanmeldung](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [DNS-Anforderungen für die Mobilität](lync-server-2013-dns-requirements-for-mobility.md)

  - [DNS-Lastenausgleich in Lync Server 2013](lync-server-2013-dns-load-balancing.md)

