---
title: 'Lync Server 2013: Unterstützte Datenbanksoftware'
TOCTitle: Unterstützte Datenbanksoftware
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398990(v=OCS.15)
ms:contentKeyID: 49295661
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Datenbanksoftware in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 unterstützt die folgenden Datenbankverwaltungssysteme:

  - **Back-End-Datenbank eines Front-End-Pools, Archivierungsdatenbank, Überwachungsdatenbank, Datenbank für beständigen Chat und Konformitätsdatenbank für beständigen Chat**
    
      - Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2012 Enterprise (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2012 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

  - **Standard Edition-Serverdatenbank und Front-End-Server-Datenbanken**
    
      - Microsoft SQL Server 2012 Express (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
        
        Wir unterstützen Patches und Upgrades von Microsoft SQL Server auf Front-End-Server und Standard Edition-Server. Wenn Sie jedoch ein Upgrade oder einen Patch auf Front-End-Server anwenden, müssen Sie Quorumanforderungen berücksichtigen. Weitere Informationen finden Sie unter [Upgraden oder Updaten von Front-End-Servern in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) und [Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    

    > [!NOTE]
    > Microsoft SQL Server 2012 Express (64-Bit-Edition) wird von Lync Server 2013 automatisch auf jedem Standard Edition-Server und jedem Front-End-Server-Server installiert.




> [!IMPORTANT]
> <UL>
> <LI>
> <P>Die 32-Bit-Version von SQL Server wird nicht von Lync Server 2013 unterstützt. Sie müssen die 64-Bit-Version verwenden.</P>
> <LI>
> <P>SQL Server Web Edition und SQL Server Workgroup Edition werden nicht unterstützt. Sie können diese Versionen nicht mit Lync Server 2013 verwenden.</P>
> <LI>
> <P>Lync Server 2013 bietet keine Unterstützung für die systemeigene Datenbankspiegelung.</P>
> <LI>
> <P>Zum Verwenden der Monitoring Server-Rolle sollten Sie SQL Server Reporting Services installieren.</P></LI></UL>



In einem Front-End-Pool kann es sich bei der Back-End-Datenbank um einen einzelnen SQL Server-Computer handeln.


> [!IMPORTANT]
> Wenn Sie Lync Server-Datenbanken mit anderen Datenbanken verbinden, wird dringend empfohlen, alle Faktoren einzubeziehen, die sich ggf. auf die Verfügbarkeit und Leistung auswirken. Zudem sollte sichergestellt werden, dass bei einem Ausfall eines Knoten der verbleibende Knoten die Last tragen kann. Zum Überprüfen der Failoverkapazitäten wird empfohlen, alle Failoverszenarien zu testen.



## Verwenden von SQL-Spiegelung und SQL-Clustering

Lync Server 2013 unterstützt die Verwendung von entweder SQL-Spiegelung oder SQL-Clustering für jede Lync Server-Datenbank. SQL-Spiegelung können Sie problemlos mit dem Topologie-Generator-Tool in Lync Server 2013 einrichten. Zum Einrichten von SQL-Failoverclustering müssen Sie SQL Server verwenden.

Lync Server 2013 unterstützt sowohl SQL-Spiegelungs- und -Clusteringtopologien für alle Bereitstellungen, einschließlich Bereitstellungen ohne bestehende Infrastruktur, sowie Organisationen, die ein Upgrade von früheren Versionen von Lync Server durchgeführt haben.

Die SQL-Clusteringunterstützung bezieht sich auf eine Aktiv/Passiv-Konfiguration. Aus Leistungsgründen sollte der passive Knoten von keiner anderen SQL-Instanz verwendet werden.

Die folgende Unterstützung wird geboten:

  - Zwei-Knoten-Failoverclustering für:
    
      - Microsoft SQL Server 2012 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

  - Failoverclustering mit bis zu sechzehn Knoten für:
    
      - Microsoft SQL Server 2012 Enterprise (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

Weitere Informationen zu SQL-Spiegelung finden Sie unter [Hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Ausführlichere Informationen zum Bereitstellen von SQL-Clustering finden Sie unter [Konfigurieren von SQL Server-Clustering](lync-server-2013-configure-sql-server-clustering.md).

Weitere Informationen zu und bewährte Verfahren für Failoverclustering in SQL Server 2012 finden Sie unter <http://technet.microsoft.com/de-de/library/hh231721.aspx>. Informationen zu Failoverclustering in SQL Server 2008 finden Sie unter <http://technet.microsoft.com/de-de/library/ms189134(v=sql.105).aspx>.

