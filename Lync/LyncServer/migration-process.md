---
title: Migrationsvorgang
TOCTitle: Migrationsvorgang
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204696(v=OCS.15)
ms:contentKeyID: 49293252
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrationsvorgang

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Das empfohlene und unterstützte Migrationsverfahren für Lync Server 2013 ist die sogenannte parallele Migration. In diesem Thema wird erläutert, warum Sie dieses Verfahren anwenden sollten. Außerdem finden Sie hier Informationen zum Thema Koexistenztest.

## Parallele Migration

Am besten wenden Sie für jede Migration das Verfahren der parallelen Migration an. Bei einer parallelen Migration stellen Sie einen neuen Server mit Lync Server 2013 parallel zu einem entsprechenden Server bereit, auf dem Lync Server 2010 ausgeführt wird, und übertragen dann die Vorgänge auf den neuen Server. Sollte es nötig sein, zu Lync Server 2010 zurückzuwechseln, müssen Sie nur die Vorgänge auf die ursprünglichen Server zurückverschieben. Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit geupgradeten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.

## Koexistenztest

Nachdem Sie Lync Server 2013 parallel zu Lync Server 2010 bereitgestellt haben, stellt die Bereitstellung einen Koexistenzteststatus von Lync Server 2013 und Lync Server 2010 dar. In diesem Status ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden können, jeder Standort verwalten werden kann und die Clients mit Benutzern der aktuellen und der Vorgängerversion kommunizieren können. Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert. Die Koexistenztestphase erstreckt sich typischerweise über die gesamte Pilottestphase für Lync Server 2013. Benutzer der Vorgängerversion werden für einen bestimmten Zeitraum nach Lync Server 2013 verschoben, um die Kompatibilität der Anwendungen sowie das ordnungsgemäße Funktionieren der Features und Funktionen sicherzustellen. Nach den Pilottests werden die Benutzer und Anwendungen in die Produktionsversion von Lync Server 2013 verschoben, und die Vorgängerpools und -anwendungen von Lync Server 2010 werden außer Betrieb genommen.

