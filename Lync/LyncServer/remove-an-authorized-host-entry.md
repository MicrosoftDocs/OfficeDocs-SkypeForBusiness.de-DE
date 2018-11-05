---
title: Entfernen eines Eintrags für autorisierte Hosts
TOCTitle: Entfernen eines Eintrags für autorisierte Hosts
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204902(v=OCS.15)
ms:contentKeyID: 49294049
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen eines Eintrags für autorisierte Hosts

 

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

In diesem Thema wird beschrieben, wie Sie einen Eintrag für einen autorisierten Host der Vorversion (in Lync Server 2013 als *Eintrag für eine vertrauenswürdige Anwendung* bezeichnet) entfernen. Sie müssen vorhandene Einträge autorisierter Hosts für alle SIP/CSTA-Gateways in Ihrer Office Communications Server 2007 R2-Bereitstellung entfernen, wenn Sie die Remoteanrufsteuerung zu einer Lync Server 2013-Bereitstellung migrieren. Sie müssen zum Entfernen von vorhandenen Einträgen für autorisierte Hosts die Verwaltungstools verwenden, die in Office Communications Server 2007 R2 enthalten sind.

## So entfernen Sie einen Eintrag für einen autorisierten Host aus einer Office Communications Server 2007 R2-Bereitstellung

1.  Öffnen Sie die Office Communications Server 2007 R2-Verwaltungskonsole.

2.  Erweitern Sie die Struktur, und klicken Sie mit der rechten Maustaste auf den Pool, in dem der autorisierte Host erstellt wurde.

3.  Klicken Sie auf **Eigenschaften** und dann auf **Front-End-Eigenschaften** .

4.  Klicken Sie auf die Registerkarte **Hostautorisierung** .

5.  Wählen Sie einen Server aus, und klicken Sie auf **Entfernen** .

6.  Klicken Sie unter **Eigenschaften** auf **OK** .

