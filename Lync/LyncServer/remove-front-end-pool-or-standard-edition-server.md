---
title: Entfernen von Front-End-Pools oder Standard Edition-Servern
TOCTitle: Entfernen von Front-End-Pools oder Standard Edition-Servern
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49890818
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen von Front-End-Pools oder Standard Edition-Servern

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

In diesem Thema erhalten Sie eine Anleitung zum Entfernen eines Front-End-Pools oder eines Standard Edition- Front-End-Servers. Beim Entfernen eines Front-End-Pools entfernen Sie jeden Front-End-Server, der zu dem Pool gehört, im Rahmen des Prozesses zum Entfernen des Pools. Wenn Sie einen Standard Edition- Front-End-Server entfernen, müssen Sie die SQL-Speicher-Definition aus dem Topologie-Generator entfernen.

## So entfernen Sie einen Front-End-Server-Pool

1.  Öffnen Sie die Topologie-Generator.

2.  Navigieren Sie zum Knoten Lync Server 2010.

3.  Erweitern Sie **Enterprise Edition-Front-End-Pools** und dann den Front-End-Pool, klicken Sie mit der rechten Maustaste auf den Front-End-Pool, den Sie entfernen möchten, und klicken Sie dann auf **Löschen** .

4.  Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann je nach Bedarf den Lync Server-Bereitstellungs-Assistenten aus.

## So entfernen Sie einen Standard Edition-Front-End-Server

1.  Öffnen Sie die Topologie-Generator.

2.  Navigieren Sie zum Knoten Lync Server 2010.

3.  Erweitern Sie **Standard Edition-Front-End-Server** , klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen** .

4.  Erweitern Sie **SQL-Speicher** , klicken Sie mit der rechten Maustaste auf die SQL Server-Datenbank, die dem Standard Edition- Front-End-Server zugeordnet ist, und klicken Sie dann auf **Löschen** .
    

    > [!IMPORTANT]
    > Sie müssen die Definition der verbundenen SQL Server-Datenbanken vom Standard Edition- Front-End-Server entfernen.



5.  Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann je nach Bedarf den Lync Server-Bereitstellungs-Assistenten aus.

