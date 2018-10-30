---
title: 'Lync Server 2013: Medienumgehung und Vermittlungsserver'
TOCTitle: Medienumgehung und Vermittlungsserver
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398719(v=OCS.15)
ms:contentKeyID: 49294720
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Medienumgehung und Vermittlungsserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die Medienumgehung ist eine Lync Server-Funktion, mit der ein Administrator die Anrufweiterleitung so konfigurieren kann, dass Datenverkehr nicht über den Vermittlungsserver verarbeitet, sondern direkt zwischen dem Benutzerendpunkt und dem PSTN-Gateway übermittelt wird. Die Medienumgehung verbessert die Anrufqualität, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden. Wenn ein Remotestandort ohne Vermittlungsserver mit einem zentralen Standort über eine oder mehrere WAN-Leitungen mit Bandbreitenbeschränkung verbunden ist, werden die Bandbreitenanforderungen durch die Medienumgehung reduziert, indem Mediendaten von einem Client am Remotestandort direkt an das lokale Gateway übermittelt werden können, ohne zunächst über die WAN-Leitung an einen Vermittlungsserver am zentralen Standort und zurück gesendet werden zu müssen. Diese geringere Medienverarbeitung trägt zudem dazu bei, dass der Vermittlungsserver mehrere Gateways steuern kann.

Die Medienumgehung und die Anrufsteuerung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.

## Siehe auch

#### Konzepte

[Anrufsteuerung und Vermittlungsserver in Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  

#### Weitere Ressourcen

[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

