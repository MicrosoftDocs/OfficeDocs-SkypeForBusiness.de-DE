---
title: Unterstützung von lync Server 2013 Datenbanksoftware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8134c9ab0fe6cd481116c8a3d17636b04c980e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Unterstützung der Datenbanksoftware in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-01_

Lync Server 2013 unterstützt die folgenden Datenbankverwaltungssysteme:

  - **Back-End-Datenbank eines Front-End-Pools, Archivierungsdatenbank, Überwachungsdatenbank, Datenbank für beständigen Chat und Konformitätsdatenbank für beständigen Chat**
    
      - Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2012 Enterprise (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2012 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

  - **Standard Edition-Server Datenbank und Front-End-Server Datenbanken**
    
      - Microsoft SQL Server 2012 Express (64-Bit-Edition). Darüber hinaus wird das neueste Service Pack empfohlen.
        
        Wir unterstützen das Patchen und Upgrade von Microsoft SQL Server auf Front-End-Servern und Standard Edition-Servern. Wenn Sie allerdings ein Upgrade oder Patch auf Front-End-Servern vornehmen, müssen Sie die Quorum Anforderungen berücksichtigen. Weitere Informationen finden Sie unter [aktualisieren oder Aktualisieren von Front-End-Servern in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) und [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64-Bit Edition) wird automatisch von lync Server 2013 auf jedem Standard Edition-Server und jedem Front-End-Server Server installiert.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Die 32-Bit-Version von SQL Server wird von lync Server 2013 nicht unterstützt. Sie müssen die 64-Bit-Version verwenden.</P>
> <LI>
> <P>SQL Server-webEdition und SQL Server Workgroup Edition werden nicht unterstützt. Sie können Sie nicht mit lync Server 2013 verwenden.</P>
> <LI>
> <P>Lync Server 2013 unterstützt die systemeigene Datenbankspiegelung.</P>
> <LI>
> <P>Um die Monitoring Server-Rolle verwenden zu können, sollten Sie SQL Server Reporting Services installieren.</P></LI></UL>



</div>

In einem Front-End-Pool kann es sich bei der Back-End-Datenbank um einen einzelnen SQL Server Computer handeln.

<div>


> [!IMPORTANT]  
> Wenn Sie lync Server Datenbanken mit anderen Datenbanken collocate, wird dringend empfohlen, alle Faktoren zu bewerten, die sich auf die Verfügbarkeit und Leistung auswirken können, sowie sicherzustellen, dass der verbleibende Knoten bei einem Ausfall des Knotens die Last verarbeiten kann. Zum Überprüfen der Failoverfunktionen wird empfohlen, alle Failover-Szenarien zu testen.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Verwenden von SQL-Spiegelung und SQL-Clustering

Lync Server 2013 unterstützt die Verwendung von SQL-Spiegelung oder SQL-Clustering für jede lync Server Datenbank. Sie können die SQL-Spiegelung ganz einfach mit dem Topologie-Generator-Tool in lync Server 2013 einrichten. Für SQL-Failoverclustering müssen Sie SQL Server für das Setup verwenden.

Lync Server 2013 unterstützt sowohl SQL-Spiegelungs-als auch SQL-Clustering-Topologien für alle Bereitstellungen, einschließlich Greenfield-Bereitstellungen und Organisationen, die von früheren Versionen von lync Server aktualisiert haben.

Die Unterstützung für SQL-Clustering ist für eine aktive/passive Konfiguration. Aus Leistungsgründen sollte der passive Knoten nicht von einer anderen SQL-Instanz gemeinsam verwendet werden.

Die folgende Unterstützung ist enthalten:

  - Failover-Clusterunterstützung mit zwei Knoten für Folgendes:
    
      - Microsoft SQL Server 2012 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

  - Failover-Clusterunterstützung für bis zu sechzehn Knoten für Folgendes:
    
      - Microsoft SQL Server 2012 Enterprise (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

Weitere Informationen zur SQL-Spiegelung finden Sie unter [Back End Server High Availability in lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Ausführliche Informationen zum Bereitstellen von SQL-Clustering finden Sie unter [configure SQL Server Clustering for lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Weitere Informationen und bewährte Methoden für die Failover-Clusterunterstützung in SQL Server 2012 finden <https://technet.microsoft.com/library/hh231721.aspx>Sie unter. Informationen zur Failover-Clusterunterstützung in SQL Server 2008 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>finden Sie unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

