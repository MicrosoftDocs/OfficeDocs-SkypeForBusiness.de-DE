---
title: 'Lync Server 2013: Dateispeicherunterstützung'
TOCTitle: Dateispeicherunterstützung
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399073(v=OCS.15)
ms:contentKeyID: 49295815
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Dateispeicherunterstützung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 verwendet für die gesamte Speicherung von Dateien den gleichen Dateispeicher. Die Dateispeicherunterstützung umfasst Folgendes:

  - Eine Dateifreigabe auf einer DAS-Lösung (Direct Attached Storage) oder auf einer SAN-Lösung (Storage Area Network), einschließlich DFS (Distributed File System), sowie auf einem RAID (Redundant Array of Independent Disks) für Dateispeicher. Nähere Informationen zu den Speicheranforderungen finden Sie unter [Technische Anforderungen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) und [Hardware- und Softwareanforderungen für den Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in der Planungsdokumentation. Nähe Informationen zu DFS für Windows Server 2008-Betriebssystem finden Sie in der "Schrittweisen Anleitung für verteilte Dateisysteme unter Windows Server 2008" unter [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).

  - Einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie einen freigegebenen Cluster verwenden, sollten Sie Clusterserver mit Windows Server 2008 oder Windows Server 2008 R2 verwenden. Das Ausführen von Clusterservern mit einer älteren Version von Windows kann dazu führen, dass einige Features aufgrund von Berechtigungsproblemen nicht zur Verfügung stehen. Verwenden Sie die Clusterverwaltung, um die Dateifreigaben zu erstellen. Nähere Informationen zur Verwendung der Clusterverwaltung finden im Microsoft Knowledge Base-Artikel 284838, "Erstellen einer Servercluster-Dateifreigabe mit Cluster.exe" unter [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).

