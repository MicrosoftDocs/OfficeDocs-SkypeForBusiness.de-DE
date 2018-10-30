---
title: 'Lync Server 2013: Neue Funktionen für Notfallwiederherstellung und hohe Verfügbarkeit'
TOCTitle: Neue Funktionen für Notfallwiederherstellung und hohe Verfügbarkeit
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204892(v=OCS.15)
ms:contentKeyID: 49293978
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue Funktionen für Notfallwiederherstellung und hohe Verfügbarkeit in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-20_

Das zentrale Hochverfügbarkeitsschema für Lync Server 2013 basiert wie in Lync Server 2010 auf Serverredundanz aufgrund von Poolbildung. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front-End-Server und Edgeserver ebenso wie für Vermittlungsserver und Directors.

Lync Server 2013 stellt neue Maßnahmen für die Notfallwiederherstellung bereit. Zu diesem Zweck können Front-End-Pools jetzt in zwei Rechenzentren gekoppelt werden. Wenn ein gekoppelter Pool ausfällt, kann ein Administrator die Benutzer von diesem Pool in den anderen Pool der Kopplung verschieben, um die weitere Nutzung des Diensts zu ermöglichen. Diese Funktion erfordert keine umfangreichen Netzwerk- oder Hardwarelösungen wie SAN-Systeme (Storage Area Network) oder Datenträgerfreigaben.

Lync Server 2013 fügt darüber hinaus die Hochverfügbarkeit für Back-End-Server hinzu. In dieser optionalen Topologie werden zwei Back-End-Server für einen Front-End-Pool bereitgestellt, und synchrone SQL-Spiegelungen für alle Lync-Datenbanken mit den Back-End-Servern werden eingerichtet.

## Siehe auch

#### Konzepte

[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

