---
title: 'Lync Server 2013: Planen der hohen Verfügbarkeit und der Notfallwiederherstellung'
TOCTitle: Planen der hohen Verfügbarkeit und der Notfallwiederherstellung
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204703(v=OCS.15)
ms:contentKeyID: 49293277
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-31_

Genau wie in Lync Server 2010 basiert das Hauptschema für hohe Verfügbarkeit für die meisten Serverrollen in Lync Server 2013 auf Serverredundanz durch Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.

In Lync Server 2013 sind neue Notfallwiederherstellungsmaßnahmen für Front-End-Pools verfügbar, da eine geografische Verteilung Ihrer Server auf zwei Rechenzentren eingeführt wurde, um die Verfügbarkeit der Dienste auch beim Ausfall eines gesamten Pools oder Standorts sicherzustellen.

In Lync Server 2013 wurde auch die hohe Back-End-Serververfügbarkeit erweitert, indem die synchrone SQL-Spiegelung für Ihre Back-End-Datenbanken unterstützt wird.

In diesem Abschnitt werden diese wichtigen Features für hohe Verfügbarkeit und Notfallwiederherstellung erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für Ihre anderen Serverrollen ausführen können.

## In diesem Abschnitt

  - [Notfallwiederherstellung eines Front-End-Pools in Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Anrufverwaltungsfunktionen für die Notfallwiederherstellung in Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

