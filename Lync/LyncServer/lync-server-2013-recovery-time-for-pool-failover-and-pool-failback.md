---
title: 'Lync Server 2013: Wiederherstellungsdauer bei einem Failover und Failback eines Pools'
TOCTitle: Wiederherstellungsdauer bei einem Failover und Failback eines Pools
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205079(v=OCS.15)
ms:contentKeyID: 49294739
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellungsdauer bei einem Failover und Failback eines Pools in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-10_

Für Pool-Failover und Pool-Failback liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 30 Minuten. Dies ist die Zeit, die erforderlich ist, bis das Failover stattfindet, nachdem Administratoren festgestellt haben, dass ein Notfall vorliegt, und die Failover-Prozeduren initiiert haben. Hierin ist die Zeit, die Administratoren für die Bewertung der Situation und die Entscheidungsfindung benötigen, nicht enthalten. Auch nicht enthalten ist die Zeit, die Benutzer nach Abschluss des Failovers für die Anmeldung benötigen.

Für Pool-Failover und Pool-Failback liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 30 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Backupdienstes verloren gehen können. Wenn ein Pool z. B. um 10:00 Uhr ausfällt und das RPO bei 30 Minuten liegt, werden die Daten, die zwischen 9:30 Uhr und 10:00 Uhr in den Pool geschrieben werden, möglicherweise nicht im Backup-Pool repliziert und gehen dann verloren.

Alle in diesem Dokument aufgeführten RTO- und RPO-Zahlen gehen davon aus, dass sich die beiden Rechenzentren in derselben Weltregion befinden und zwischen den Standorten eine Highspeed-Übertragung mit geringer Latenz stattfindet. Die Zahlen wurden für einen Pool mit 40.000 konkurrierend aktiven Benutzern und 200.000 für Lync aktivierten Benutzern gemessen. Eingehalten wird ein vordefiniertes Benutzermodell, das keinen Rückstand der Datenreplikation vorsieht. Die Zahlen können sich aufgrund von Leistungstest und Leistungsvalidierungen ändern.

