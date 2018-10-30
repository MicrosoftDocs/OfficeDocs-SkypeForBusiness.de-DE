---
title: Zuordnen von Subnetzen zu Netzwerkstandorten für die Medienumgehung
TOCTitle: Zuordnen von Subnetzen zu Netzwerkstandorten für die Medienumgehung
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398401(v=OCS.15)
ms:contentKeyID: 49294120
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuordnen von Subnetzen zu Netzwerkstandorten für die Medienumgehung

 

_**Letztes Änderungsdatum des Themas:** 2012-09-12_


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie die globalen Einstellungen für die Medienumgehung sowie die Netzwerkregion und Netzwerkstandorte für die Medienumgehung konfiguriert haben.



Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein. Anhand dieser Subnetzinformationen wird der Netzwerkstandort ermittelt, an dem sich ein Endpunkt befindet. Wenn die Standorte beider Teilnehmer einer Sitzung bekannt sind, kann die Medienumgehung das Ziel ermitteln, an das die Mediendaten zur Verarbeitung gesendet werden sollen.

Für die Medienumgehung gelten keine speziellen Anforderungen für die Zuordnung von Subnetzen zu Netzwerkstandorten. Führen Sie die unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) beschriebenen Schritte aus, um eine Zuordnung zwischen den Subnetzen und Netzwerkstandorten in Ihrer Topologie zu erstellen.

## Nächste Schritte: Erstellen von Bandbreitenrichtlinienprofilen

Nachdem Sie die Subnetze und Netzwerkstandorte für die Medienumgehung zugeordnet haben, müssen Sie mindestens ein Bandbreitenrichtlinienprofil erstellen, mit dem Subnetze für die Medienumgehung in Subnetze mit und ohne gute Konnektivität unterteilt werden. Alle Subnetze innerhalb einer Netzwerkregion mit Netzwerkstandorten, für die keine Bandbreiteneinschränkungen gelten, verfügen über eine gute Konnektivität. Für diese Subnetze kann daher die Medienumgehung verwendet werden.

Die Schritte zum Konfigurieren von Bandbreitenrichtlinienprofilen sind unter [Erstellen von Bandbreitenrichtlinienprofilen in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) beschrieben.

