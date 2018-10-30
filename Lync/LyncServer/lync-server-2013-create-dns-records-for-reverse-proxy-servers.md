---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverseproxyserver'
TOCTitle: Erstellen von DNS-Einträgen für Reverseproxyserver
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429719(v=OCS.15)
ms:contentKeyID: 49295139
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-29_

Erstellen Sie externe DNS-A-Einträge, die auf die öffentliche externe Schnittstelle Ihrer Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Ihres Forefront Threat Management Gateway 2010 Servers oder des Internet Information Server-Routings für Anwendungsanforderungen verweisen, wie unter [Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md) beschrieben. Sie benötigen DNS-Einträge für die externen Webdienst-FQDNs für jeden Pool, die Director (oder Directorpool) und jede einfache URL.

Für die minimalen DNS-Einträge für die Clientauflösung für Reverseproxy müssen die folgenden Einträge erstellt werden:

  - Host (A)-Eintrag/-Einträge, der/die den veröffentlichten externen Webdienst für Directors- und Director-Pools definiert/definieren (beispielsweise **webdirext.contoso.com** )

  - Host (A)-Eintrag/-Einträge, der/die den veröffentlichten externen Webdienst für externe Webdienste definiert bzw. definieren, die auf beliebigen Front-End-Pools- und Standard Edition-Server-Rollen gehostet werden (beispielsweise **webext.contoso.com** )

  - Host (A)-Einträge für einfache URLs (beispielsweise **dialin.contoso.com** und **meet.contoso.com** )

  - Host (A)-Einträge für den Lync Discover External-Eintrag, bietet auch einen Verweis auf AutoDiscover für alle Web-Apps, einschließlich Lync Web App, Planer und Mobilität (beispielsweise **lyncdiscover.contoso.com** )

  - Host (A)-Einträge für die Office Web Apps-Server-URL (z. B. **officewebapp01.contoso.com** )

Ausführliche Informationen finden Sie unter [DNS-Zusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

