---
title: Migrationsprozess
TOCTitle: Migrationsprozess
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205181(v=OCS.15)
ms:contentKeyID: 49295134
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrationsprozess

 

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Das empfohlene und unterstützte Migrationsverfahren für Lync Server 2013 ist die so genannte parallele Migration. In diesem Thema wird beschrieben, weshalb Sie die parallele Migration verwenden sollten, und es enthält zudem Informationen über die Koexistenz.

## Parallele Migration

Am besten wenden Sie für nahezu jede Migration das Verfahren der parallelen Migration an. Bei einer parallelen Migration stellen Sie einen neuen Server mit Lync Server 2013 parallel zu einem entsprechenden Server bereit, auf dem Office Communications Server 2007 R2 ausgeführt wird, und übertragen dann die Vorgänge auf den neuen Server. Sollte es nötig sein, ein Rollback auf Office Communications Server 2007 R2 vorzunehmen, müssen Sie nur die Vorgänge auf die ursprünglichen Server zurückverschieben. Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.

## Koexistenztest

Nachdem Sie Lync Server 2013 parallel zu Office Communications Server 2007 R2, bereitgestellt haben, stellt die Topologie einen Koexistenzteststatus der Bereitstellung von Lync Server 2013 und Office Communications Server 2007 R2 dar. In diesem Status ist es wichtig zu testen bzw. zu überprüfen, ob Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und Legacybenutzern kommunizieren können. Vor dem Migrieren aller Benutzer ist es sehr wichtig, dass Sie den Status jeder Bereitstellung verstehen und sicherstellen, dass jede Bereitstellung funktioniert und ordnungsgemäß ausgeführt wird. Diese Koexistenztestphase erstreckt sich gewöhnlich über die gesamte Pilottestphase von Lync Server 2013. Legacybenutzer werden für einen bestimmten Zeitraum nach Lync Server 2013 verschoben, um die Kompatibilität der Anwendungen sowie das ordnungsgemäße Funktionieren der Features und Funktionen sicherzustellen. Nach den Pilottests werden die Benutzer und Anwendungen in die Produktionsversion von Lync Server 2013 verschoben, und die Vorgängerpools und -anwendungen von Office Communications Server 2007 R2 werden außer Betrieb genommen.

