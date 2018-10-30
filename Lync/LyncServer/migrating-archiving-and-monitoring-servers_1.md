---
title: Migrieren von Archivierungsservern und Monitoring Servern
TOCTitle: Migrieren von Archivierungsservern und Monitoring Servern
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49890834
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Archivierungsservern und Monitoring Servern

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Wenn Sie einen Archivierungsserver und Monitoring Server in Ihrem Office Communications Server 2007 R2 bereitgestellt haben, können Sie diese Server nach der Migration Ihrer Front-End-Pools in Ihrer Lync Server 2013-Umgebung bereitstellen. Wenn Archivierungs- und Überwachungsfunktionen in Ihrer Organisation jedoch entscheidend sind, sollten Sie Ihrem Pilotpool vor der Migration Archivierungsserver und Monitoring Server hinzufügen, damit diese Funktionen auch während des Migrationsvorgangs zur Verfügung stehen.

Wenn Sie während der Phase der Migration und Koexistenz Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:

  - Archivierungs- und Überwachungsdaten werden nicht in die Lync Server 2013-Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebsetzung der Vorversionsumgebung sichern, sind Bestandteil der aufgezeichneten Aktivitäten von Office Communications Server 2007 R2.

  - Die Office Communications Server 2007 R2-Version des Archivierungsservers und Monitoring Servers kann nur einem Office Communications Server 2007 R2-Front-End-Pool zugeordnet werden. Unter Lync Server 2013 werden Archivierung und Monitoring nicht mehr als Serverrollen behandelt, sondern als in den Lync Server 2013-Front-End-Pool integrierte Dienste.

  - Während der Koexistenz der Vorversionsbereitstellung und der Lync Server 2013-Bereitstellung sammelt die Office Communications Server 2007 R2-Version des Archivierungsservers und Monitoring Servers Daten von Benutzern, die in Office Communications Server 2007 R2-Pools verwaltet werden. Die Lync Server 2013-Version des Archivierungsservers und Monitoring Servers sammelt Daten von Benutzern, die in Lync Server 2013-Pools verwaltet werden.
    

    > [!NOTE]
    > Während der Migrationsphase, wenn Sie die Edgeserver der Vorversion noch zusammen mit dem neuen Lync Server 2013-Pilotpool verwenden, sammelt die Office Communications Server 2007 R2-Version des Archivierungsservers noch immer Daten von Benutzern, die in Office Communications Server 2007 R2-Pools verwaltet werden, und die Lync Server 2013-Version des Archivierungsservers sammelt noch Daten von Benutzern, die in Lync Server 2013-Pools verwaltet werden.



  - Bei Verwendung der Archivierungs- und Überwachungslösung eines Drittanbieters zusammen mit dem Archivierungsserver und Monitoring Server besprechen Sie mit Ihrem Anbieter, wann und wie die Drittanbieterlösung mit Lync Server 2013 integriert werden sollte.

