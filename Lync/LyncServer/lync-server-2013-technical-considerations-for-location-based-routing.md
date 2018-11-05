---
title: 'Lync Server 2013: Technische Überlegungen zum standortbasierten Routing'
TOCTitle: Technische Überlegungen zum standortbasierten Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994027(v=OCS.15)
ms:contentKeyID: 52056311
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Überlegungen zum standortbasierten Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Wenn Sie standortbasiertes Routing planen, sollten Sie die Auswirkungen der folgenden Szenarios beachten.

## Notfallwiederherstellung

Bei einem Failover vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen des normalen Betriebs für den primären Pool wird standortbasiertes Routing jederzeit während einer Notfall- oder Wiederherstellungsprozedur erzwungen.

## Survivable Branch Appliance (SBA)

Ein Konfigurieren von standortbasiertem Routing wirkt sich auf die Planung aus, wo die Gateways bereitgestellt werden sollten, die Ihren Survivable Branch-Anwendungen zugewiesen sind. Das Gateway, das Ihrer SBA zugewiesen ist, muss sich im selben Netzwerkstandort befinden wie Ihre Survivable Branch-Anwendung. Andernfalls erhalten Benutzer, die auf Ihrer Survivable Branch-Anwendung gehostet werden, keine Berechtigung zum Führen von ausgehenden Anrufen, wenn standortbasiertes Routing konfiguriert ist. Wenn die WAN-Verbindung zwischen Ihrer Survivable Branch-Anwendung und dem Hauptstandort unterbrochen ist, werden die Beschränkungen des standortbasierten Routings weiterhin erzwungen.

## Siehe auch

#### Weitere Ressourcen

[Planung des standortbasierten Routings in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

