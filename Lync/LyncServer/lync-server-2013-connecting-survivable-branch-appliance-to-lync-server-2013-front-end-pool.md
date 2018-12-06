---
title: 'Lync Server 2013: Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool'
TOCTitle: Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49890711
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool

 

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Jede Survivable Branch-Anwendung (SBA) ist einem Front-End-Pool zugeordnet, der als Sicherungsregistrierung für die SBA dient. Wenn der Front-End-Pool auf Lync Server 2013 aktualisiert wird, muss die Zuordnung der SBA zum Front-End-Pool aufgehoben werden, während der Front-End-Pool aktualisiert wird. Nach der Aktualisierung des Front-End-Pools kann die SBA dem Front-End-Pool wieder zugeordnet werden. Dazu muss die SBA aus der Topologie im Topologie-Generator gelöscht und anschließend erneut zum Topologie-Generator hinzugefügt werden. Benutzer auf der SBA müssen auf einen anderen Front-End-Pool verschoben werden, bevor die SBA aus der Topologie entfernt wird. Nach dem erneuten Hinzufügen der SBA zur Topologie können diese Benutzer auf die SBA zurückverschoben werden.

Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:

1.  Verschieben Sie die Zweigstellenbenutzer auf der SBA in einen anderen Front-End-Pool.

2.  Entfernen Sie die SBA aus Ihrer Topologie, um die bestehende Zuordnung des bestehenden Front-End-Pools als Sicherungsregistrierung aufzuheben.

3.  Aktualisieren Sie Front-End-Pool auf Microsoft Lync Server 2013.

4.  Fügen Sie die SBA wieder Ihrer Topologie hinzu.

5.  Ordnen Sie der SBA den neuen Front-End-Pool als Sicherungsregistrierung zu.

6.  Verschieben Sie die Zweigstellenbenutzer zurück auf die SBA.

## In diesem Abschnitt

  - [Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2010 Survivable Branch Appliance zu einer Topologie](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

