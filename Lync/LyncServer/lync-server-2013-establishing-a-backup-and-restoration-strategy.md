---
title: Einrichten einer Sicherungs- und Wiederherstellungsstrategie
TOCTitle: Einrichten einer Sicherungs- und Wiederherstellungsstrategie
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202195(v=OCS.15)
ms:contentKeyID: 52056494
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten einer Sicherungs- und Wiederherstellungsstrategie

 

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Bevor Sie einen Sicherungs- und Wiederherstellungsplan für Lync Server entwickeln können, müssen Sie eine Strategie entwickeln, die mit Ihren Organisationszielen konform ist. Das Entwickeln einer effektiven Sicherungs- und Wiederherstellungsstrategie erfordert Folgendes:

  - Festlegen von Unternehmensprioritäten

  - Identifizieren der Sicherungs- und Wiederherstellungsanforderungen

## Festlegen von Unternehmensprioritäten

Bewerten Sie die Unternehmensprioritäten Ihrer Organisation. In der Regel umfassen die primären Unternehmensprioritäten, die Ihre Sicherungs- und Wiederherstellungsstrategie beeinflussen, die Folgenden:

  - Anforderungen an Geschäftskontinuität

  - Datenvollständigkeit

  - Datenkritikalität

  - Portabilitätsanforderungen

  - Kosteneinschränkungen

Geschäftsanforderungen wie diese helfen beim Bestimmen der Vereinbarungen zum Servicelevel (SLA), die Sie mit Ihren Kunden entwickeln. Vereinbarungen zum Servicelevel haben erheblichen Einfluss auf Ihre Sicherungs- und Wiederherstellungsstrategie.

## Identifizieren der Sicherungs- und Wiederherstellungsanforderungen

Ihre Unternehmensprioritäten und Vereinbarungen zum Servicelevel dienen zum Bestimmen der Lync Server-Sicherungs- und Wiederherstellungsanforderungen Ihrer Organisation. Identifizieren und dokumentieren Sie Ihre Anforderungen für Folgendes:

  - **Häufigkeit von Sicherungen**   Beachten Sie, dass Lync Server abgesehen von Front-End-Pools in einer Paarbeziehung gemäß der Beschreibung in [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md) nur das einfache Wiederherstellungsmodell unterstützt, was bedeutet, dass die letzte vollständige Sicherung wiederhergestellt wird. Planen Sie sorgfältig, wie oft eine vollständige Sicherung durchgeführt werden muss. Ausführliche Informationen zu bewährten Methoden bei der Sicherungshäufigkeit finden Sie unter [Bewährte Methoden für die Sicherung und Wiederherstellung](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Sicherungs- und Wiederherstellungstools**   Geben Sie an, wer diese Tools benutzen soll und auf welchen Computern. Ausführliche Informationen über die in diesem Thema behandelten Tools und die erforderlichen Berechtigungen finden Sie unter [Anforderungen für die Sicherung und Wiederherstellung: Tools und Berechtigungen](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Sicherungsspeicherort**   Legen Sie fest, ob Sicherungen lokal oder remote gespeichert werden, und berücksichtigen Sie dabei Sicherheit und Zugänglichkeit. Legen Sie das für die Sicherungen zu verwendende Medium fest.

  - **Hardware- und Softwareanforderungen**   Identifizieren und dokumentieren Sie Ihre spezifischen Hardware- und Softwareanforderungen, einschließlich der Hardware für die Sicherungsspeicherung und Wiederherstellung bestimmter Komponenten sowie Software und Netzwerkverbindungen, die zur Unterstützung der Sicherung und Wiederherstellung benötigt werden. Beachten Sie beim Entwickeln Ihrer Hardware- und Softwareanforderungen die verschiedenen sich ergebenden Wiederherstellungsszenarien.

  - **Wiederherstellungsszenarien**   Hier sind die Wiederherstellungsprozesse für folgende Szenarien beschrieben:
    
      - Ein Lync Server-Pool fällt aus. Dieses Szenario erfordert die Neuerstellung aller Server im Pool.
    
      - Ein Standard Edition-Server fällt aus. Dieses Szenario erfordert die Neuerstellung des Servers auf einem neuen oder bereinigten Computer sowie das Wiederherstellen der Datenbanken.
    
      - Verlust des zentralen Verwaltungsspeicher. Dieses Szenario erfordert mindestens die Wiederherstellung und Veröffentlichung des zentralen Verwaltungsspeicher.
    
      - Verlust eines Back-End-Servers, wenn der zentralen Verwaltungsspeicher weiterhin ordnungsgemäß funktioniert. Dieses Szenario erfordert die Neuerstellung des Servers auf einem neuen oder bereinigten Computer sowie das Wiederherstellen der Datenbanken.
    
      - Ein Server, der Mitglied in einem Lync Server-Pool ist, fällt aus. Dieses Szenario erfordert die Neuerstellung des Servers auf einem neuen oder bereinigten Computer.
    
      - Ein Dateispeicher fällt aus. Dieses Szenario erfordert die Wiederherstellung des Dateiservers oder Dateiclusters.
    
      - Eine Archivierungs- oder Überwachungsdatenbank oder eine Datenbank für beständigen Chat fällt aus. Dieses Szenario erfordert die Wiederherstellung der Datenbanken, und wenn es sich um wichtige Daten für Ihre Organisation handelt, müssen die Daten wiederhergestellt werden. Daten aus den Datenbanken für Archivierung, Überwachung und beständigen Chat sind nicht erforderlich, um Lync Server wieder zum Laufen zu bringen.

