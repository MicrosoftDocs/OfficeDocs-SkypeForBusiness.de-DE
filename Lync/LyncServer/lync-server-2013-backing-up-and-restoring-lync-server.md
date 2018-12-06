---
title: Sichern und Wiederherstellen von Lync Server 2013
TOCTitle: Sichern und Wiederherstellen von Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202160(v=OCS.15)
ms:contentKeyID: 52056280
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sichern und Wiederherstellen von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In diesem Abschnitt finden Sie bewährte Methoden zum Sichern Ihrer Lync Server 2013-Daten und zum Wiederherstellen nach einem Ausfall. Diese bewährten Methoden gelten für die folgenden Situationen:

  - Ein gesamter Lync Server-Pool beliebigen Typs (Front-End-Server, Edgeserver, Vermittlungsserver, Server für beständigen Chat oder Director) oder ein Einzelserver in einem dieser Pools.

  - Der zentraler Verwaltungsserver

  - Ein Standard Edition-Server

  - Ein Enterprise Edition-Back-End-Server

  - Ein Dateispeicher

  - Eine Archivierungsdatenbank, eine Überwachungsdatenbank oder eine Datenbank für beständigen Chat

Dieser Abschnitt enthält keine Informationen zum Wiederherstellen eines gesamten Standorts oder zum Entwickeln eines Standbystandorts. Ausführliche Informationen zum Entwickeln einer Notfallwiederherstellungslösung mit gekoppelten Front-End-Pools finden Sie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Hierbei handelt es sich um die empfohlene Methode bei der Planung der Notfallwiederherstellung.

Wenn Sie gekoppelte Front-End-Pools bereitgestellt haben und in einem dieser Pools ein nicht behebbarer Fehler auftritt, können Sie diesen Pool mit einem neuen vollqualifizierten Domänennamen (FQDN) im gekoppelten Pool wiederherstellen. Einzelheiten zu den für diese Wiederherstellung erforderlichen Schritten finden Sie unter [Ausführen eines Failovers für einen Pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Wenn Sie außerdem später einen Pool mit einem nicht behebbaren Fehler erneut erstellen möchten, der Teil eines Front-End-Paares war, können Sie dazu die Schritte in [Durchführen eines ABC-Failovers im Front-End-Pool](lync-server-2013-performing-an-abc-front-end-pool-failover.md) verwenden.

Bei der in diesem Dokument beschriebenen Methodik werden besondere Überlegungen während der Planungsphase mit berücksichtigt. Ausführliche Informationen finden Sie unter [Einrichten eines Sicherungs- und Wiederherstellungsplans](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

## In diesem Abschnitt

  - [Vorbereiten der Lync Server-Sicherung und -Wiederherstellung](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Sichern von Daten und Einstellungen](lync-server-2013-backing-up-data-and-settings.md)

  - [Wiederherstellen von Daten und Einstellungen](lync-server-2013-restoring-data-and-settings.md)

  - [Arbeitsblätter zur Sicherung und Wiederherstellung](lync-server-2013-backup-and-restoration-worksheets.md)

