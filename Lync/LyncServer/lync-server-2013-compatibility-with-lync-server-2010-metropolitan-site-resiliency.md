---
title: Lync Server 2013-Kompatibilität mit der Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010
TOCTitle: Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204715(v=OCS.15)
ms:contentKeyID: 49293310
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010

 

_**Letztes Änderungsdatum des Themas:** 2014-03-19_

Die für Lync Server 2010 unterstützte Ausfallsicherheitslösung für innerstädtische Standorte wird für Lync Server 2013 nicht unterstützt. Diese Lösung beinhaltete einen einzelnen Front-End-Pool, der zwei Rechenzentren im selben innerstädtischen Gebiet umfasst.

Die Ausfallsicherheitslösung für innerstädtische Standorte wurde für die Wiederherstellung nach dem Verlust eines vollständigen Rechenzentrums entwickelt. Wenn Sie Ihren Pool über zwei Rechenzentren verteilen, stellen Sie normalerweise die Hälfte Ihrer Front-Ends in ein Rechenzentrum und die andere Hälfte in das zweite Rechenzentrum. Wenn Sie ein vollständiges Rechenzentrum verlieren, haben Sie die Hälfte Ihrer Frond-End-Server verloren. Das kann zu Problemen mit dem neu verteilten Systemmodell für Front-End-Pools in Lync Server 2013 führen. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

