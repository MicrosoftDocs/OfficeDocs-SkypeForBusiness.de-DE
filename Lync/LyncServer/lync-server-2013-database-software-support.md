---
title: 'Lync Server 2013: Unterstützte Datenbanksoftware'
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
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Unterstützte Datenbanksoftware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-01_

Lync Server 2013 unterstützt die folgenden Datenbank-Management Systeme:

  - **Back-End-Datenbank eines Front-End-Pools, Archivierungsdatenbank, Überwachungsdatenbank, Datenbank für beständigen Chat und Konformitätsdatenbank für beständigen Chat**
    
      - Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2012 Enterprise (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2012 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

  - **Standard Edition-Server Datenbank und Front-End-Server Datenbanken**
    
      - Microsoft SQL Server 2012 Express (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
        
        Wir unterstützen das Patchen und Aktualisieren von Microsoft SQL Server auf Front-End-Servern und Standard Edition-Servern. Wenn Sie jedoch auf Front-End-Servern jede Art von Upgrade oder Patch vornehmen, müssen Sie die Quorum Anforderungen berücksichtigen. Weitere Informationen finden Sie unter [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) und [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64-Bit Edition) wird von lync Server 2013 auf jedem Standard Edition-Server und jedem Front-End-Server automatisch installiert.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 unterstützt nicht die 32-Bit-Edition von SQL Server. Sie müssen die 64-Bit-Version verwenden.</P>
> <LI>
> <P>SQL Server Web Edition und SQL Server Arbeitsgruppe Edition werden nicht unterstützt. Sie können Sie nicht mit lync Server 2013 verwenden.</P>
> <LI>
> <P>Lync Server 2013 unterstützt die systemeigene Datenbankspiegelung.</P>
> <LI>
> <P>Wenn Sie die Monitoring Server-Rolle verwenden möchten, sollten Sie SQL Server Reporting Services installieren.</P></LI></UL>



</div>

In einem Front-End-Pool kann die Back-End-Datenbank ein einzelner SQL Server-Computer sein.

<div>


> [!IMPORTANT]  
> Wenn Sie lync Server-Datenbanken mit anderen Datenbanken collocate, empfehlen wir dringend, alle Faktoren zu bewerten, die sich auf die Verfügbarkeit und Leistung auswirken können, und sicherzustellen, dass der verbleibende Knoten die Last verarbeiten kann, wenn ein Knoten fehlschlägt. Zum Überprüfen von Failoverfunktionen empfiehlt es sich, alle Failover-Szenarien zu testen.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Verwenden von SQL-Spiegelung und SQL-Clustering

Lync Server 2013 unterstützt die Verwendung von SQL-Spiegelung oder SQL-Clustering für jede lync Server-Datenbank. Sie können die SQL-Spiegelung auf einfache Weise mit dem Tool Topologie-Generator in lync Server 2013 einrichten. Zum Einrichten von SQL-Failoverclustering müssen Sie SQL Server verwenden.

Lync Server 2013 unterstützt sowohl SQL-Spiegelungs-als auch SQL-Cluster-Topologien für alle Bereitstellungen, einschließlich Greenfield-Bereitstellungen und Organisationen, die von früheren Versionen von lync Server aktualisiert wurden.

Die SQL-Clusteringunterstützung bezieht sich auf eine Aktiv/Passiv-Konfiguration. Aus Leistungsgründen sollte der passive Knoten von keiner anderen SQL-Instanz verwendet werden.

Die folgende Unterstützung wird geboten:

  - Zwei-Knoten-Failoverclustering für:
    
      - Microsoft SQL Server 2012 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

  - Failoverclustering mit bis zu sechzehn Knoten für:
    
      - Microsoft SQL Server 2012 Enterprise (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
      - Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.

Weitere Informationen zur SQL-Spiegelung finden Sie unter [Back-End-Server – höhere Verfügbarkeit in lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Details zum Bereitstellen von SQL-Clustering finden Sie unter [Konfigurieren des SQL Server-Clusters für lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Weitere Informationen und bewährte Methoden für die Failover-Clusterunterstützung in SQL Server 2012 finden <http://technet.microsoft.com/en-us/library/hh231721.aspx>Sie unter. Informationen zum Failover-Clustering in SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>finden Sie unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

