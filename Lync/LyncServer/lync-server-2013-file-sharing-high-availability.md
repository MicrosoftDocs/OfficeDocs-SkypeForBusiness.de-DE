---
title: 'Lync Server 2013: Hohe Verfügbarkeit der Dateifreigabe'
TOCTitle: Hohe Verfügbarkeit der Dateifreigabe
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205203(v=OCS.15)
ms:contentKeyID: 49295198
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hohe Verfügbarkeit der Dateifreigabe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-03-30_

Um hohe Verfügbarkeit für die Lync Server-Dateifreigabe innerhalb eines Rechenzentrums sicherzustellen, können Sie DFS (Distributed File System) verwenden. DFS unterstützt Failover von einem Dateiserver auf einen anderen Dateiserver innerhalb des gleichen Rechenzentrums. Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden.

Abhängig von der Größe Ihres Netzwerks und der gewünschten Ausfallsicherheit können Sie ein Serverpaar zum Hosten von sämtlichen Dateifreigaben eines Standorts oder ein Paar je Front-End-Pool verwenden.

DFS ist ein "Best Effort"-Mechanismus für die Dateireplikation ohne veröffentlichte Zusagen für Wiederherstellungszeit (Recovery Time Objective - RTO) oder Wiederherstellungspunkt (Recovery Point Objective - RPO). Der Failover zwischen den DFS-Servern sollte schnell abgeschlossen werden, jedoch kann eine Verzögerung bei der Datenreplikation verhindern, dass Benutzer ihre laufende Arbeit fortsetzen können, wenn der Failover auftritt.

Wenn Sie DFS verwenden und Datenspeicher bei der Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben öfters speichern, zum Beispiel alle vier bis acht Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt auf dem ausgefallenen Server auf den anderen Server wiederherzustellen, der mit dem Server kombiniert ist, welcher jetzt nicht verfügbar ist.

