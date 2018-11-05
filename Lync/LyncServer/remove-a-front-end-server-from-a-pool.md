---
title: Entfernen eines Front-End-Servers aus einem Pool
TOCTitle: Entfernen eines Front-End-Servers aus einem Pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49890794
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen eines Front-End-Servers aus einem Pool

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Der Front-End-Server von Microsoft Lync Server 2010 Enterprise Edition kann nicht als eigenständiger Computer ausgeführt werden. Er muss als Front-End-Pool definiert werden, selbst wenn nur ein einziger Computer im Pool enthalten ist.

Dieses Thema unterstützt Sie beim Entfernen eines einzelnen Front-End-Servers aus einem vorhandenen Front-End-Pool. Wenn der Front-End-Server der letzte Server im Pool ist oder wenn Sie den Pool vollständig entfernen, finden Sie entsprechende Informationen unter [Entfernen von Front-End-Pools oder Standard Edition-Servern](remove-front-end-pool-or-standard-edition-server.md). Es besteht keine Notwendigkeit, die einzelnen Front-End-Server zu entfernen, ehe Sie den Front-End-Pool entfernen. Wenn Sie den Pool entfernen, entfernen Sie damit jeden einzelnen Front-End-Server.

## So entfernen Sie einen Front-End-Server aus einem Pool

1.  Öffnen Sie den Lync Server 2013-Front-End-Server, und öffnen Sie dann den Topologie-Generator.

2.  Navigieren Sie zum Knoten Lync Server 2010.

3.  Erweitern Sie **Enterprise Edition-Front-End-Pools** , erweitern Sie den Front-End-Pool mit dem zu entfernenden Front-End-Server, klicken Sie mit der rechten Maustaste auf den zu entfernenden Front-End-Server, und klicken Sie dann auf **Löschen** .

