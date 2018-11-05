---
title: Migrieren von Archivierungsservern und Monitoring Servern
TOCTitle: Migrieren von Archivierungsservern und Monitoring Servern
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205015(v=OCS.15)
ms:contentKeyID: 49294464
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Archivierungsservern und Monitoring Servern

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Wenn Sie einen Archivierungsserver und Monitoring Server in Ihrer Lync Server 2010-Umgebung bereitgestellt haben, können Sie diese Server nach der Migration Ihrer Front-End-Pools in Ihrer Lync Server 2013-Umgebung bereitstellen. Wenn Archivierungs- und Überwachungsfunktionen in Ihrer Organisation jedoch entscheidend sind, sollten Sie Ihrem Lync Server 2013-Pilotpool vor der Migration Archivierungsserver und Monitoring Server hinzufügen, damit diese Funktionen auch während des Migrationsvorgangs zur Verfügung stehen.

Wenn Sie während des Migrationsvorgangs Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:

  - Archivierungs- und Überwachungsdaten werden nicht in die Lync Server 2013-Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebsetzung der Vorversionsumgebung sichern, sind Bestandteil der aufgezeichneten Aktivitäten der Lync Server 2010-Umgebung.

  - Die Lync Server 2010-Version des Archivierungsservers und Monitoring Servers kann nur einem Lync Server 2010-Front-End-Pool zugeordnet werden. Unter Lync Server 2013 werden Archivierung und Monitoring nicht mehr als Serverrollen behandelt, sondern als in den Lync Server 2013-Front-End-Pool integrierte Dienste.

  - Während der Koexistenz der Vorversionsbereitstellung und der Lync Server 2013-Bereitstellung sammelt die Lync Server 2010-Version des Archivierungsservers und Monitoring Servers Daten von Benutzern, die in Lync Server 2010-Pools verwaltet werden. Unter Lync Server 2013 werden vom Archivierungsserver und vom Monitoring Server Daten von Benutzern gesammelt, die in Lync Server 2013-Pools verwaltet werden.
    

    > [!NOTE]
    > Wenn Sie während des Migrationsvorgangs den Edgeserver der Vorversion noch zusammen mit dem neuen Lync Server 2013-Pilotpool verwenden, sammelt die Lync Server 2010-Version des Archivierungsservers noch immer Daten von Benutzern, die in Lync Server 2010-Pools verwaltet werden, und unter Lync Server 2013 werden vom Archivierungsserver noch Daten von Benutzern gesammelt, die in Lync Server 2013-Pools verwaltet werden.



  - Bei Verwendung der Archivierungs- und Überwachungslösung eines Drittanbieters zusammen mit dem Archivierungsserver und Monitoring Server unter Lync Server 2013 besprechen Sie mit Ihrem Anbieter, wann und wie die Drittanbieterlösung mit Lync Server 2013 integriert werden sollte.

