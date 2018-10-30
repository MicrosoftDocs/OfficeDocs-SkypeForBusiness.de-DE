---
title: 'Lync Server 2013: Failover des zentralen Verwaltungsspeichers'
TOCTitle: Failover des zentralen Verwaltungsspeichers
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205376(v=OCS.15)
ms:contentKeyID: 49295901
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Failover des zentralen Verwaltungsspeichers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Im zentralen Verwaltungsspeicher befinden sich Konfigurationsdaten über die Server und Dienste Ihrer Lync 2013-Bereitstellung. Er stellt ein zuverlässiges, schematisiertes Repository für Daten dar, die Sie für die Definition, Einrichtung, Wartung, Verwaltung, Beschreibung und den Betrieb einer Lync 2013-Bereitstellung benötigen. Darüber hinaus überprüft er die Daten, um eine konsistente Konfiguration zu gewährleisten.

Jede Lync-Bereitstellung enthält einen zentralen Verwaltungsspeicher, der vom Back-End-Server eines Front-End-Pools gehostet wird.

Wenn Sie eine Poolpaarung erstellen, die den Pool mit dem zentralen Verwaltungsspeicher enthält, wird im Sicherungspool eine zentralen Verwaltungsspeicher-Sicherungsdatenbank eingerichtet, wobei die zentralen Verwaltungsspeicher-Dienste in beiden Pools installiert werden. Eine der beiden zentralen Verwaltungsspeicher-Datenbanken ist dabei immer die aktive Masterdatenbank, die andere befindet sich im Standbymodus. Der Inhalt wird durch den Sicherungsdienst vom aktiven Master zur Standbydatenbank repliziert.

Während eines Poolfailovers, von dem die Pools betroffen sind, die den zentralen Verwaltungsspeicher hosten, muss der Administrator vor dem Failover des Front-End-Pools einen Failover des zentralen Verwaltungsspeichers durchführen.

Nach der Behebung des Notfalls ist es nicht erforderlich, einen Failback des zentralen Verwaltungsspeichers durchzuführen. Nach einer Reparatur kann der zentrale Verwaltungsspeicher im ursprünglichen Sicherungspool der aktive Master bleiben.

Die Entwicklungsziele für den zentralen Verwaltungsspeicher-Failover des zentralen Verwaltungsspeichers sind 5 Minuten für die Wiederherstellungsdauer (Recovery Time Objective, RTO) und 5 Minuten für den Wiederherstellungspunkt (Recovery Point Objective, RPO).

