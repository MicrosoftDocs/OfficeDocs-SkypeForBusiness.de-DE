---
title: 'Lync Server 2013: Ändern des einem Front-End-Pool zugeordneten Edgepools'
TOCTitle: Ändern des einem Front-End-Pool zugeordneten Edgepools
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49890705
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Wenn ein Edgepool ausfällt, aber der Front-End-Pool an demselben Standort noch ausgeführt wird, müssen Sie den Front-End-Pool so konfigurieren, dass er einen Edgepool an einem anderen Standort verwendet, bis der ausgefallene Edgepool wiederhergestellt ist.

## Ändern des einem Front-End-Pool zugeordneten Edgepools

1.  Navigieren Sie im Topologie-Generator zum Namen des Front-End-Pools, den Sie ändern möchten.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten** .

3.  Wählen Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** im Dropdownfeld den Edgepool aus, den Sie diesem Front-End-Pool zuordnen möchten.

4.  Klicken Sie auf **OK** .

## Siehe auch

#### Konzepte

[Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

