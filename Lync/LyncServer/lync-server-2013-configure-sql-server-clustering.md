---
title: 'Lync Server 2013: Konfigurieren von SQL Server Clustering'
description: 'Lync Server 2013: Konfigurieren von SQL Server Clustering.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4b81b62d086de27659f564427ad6adde99ecac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576751"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Konfigurieren von SQL Server Clustering für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-01-10_

Microsoft lync Server 2013 unterstützt Clustering für SQL Server 2012 und SQL Server 2008 R2. Ausführliche Informationen zu den unterstützten Funktionen finden Sie unter [Database Software Support in lync Server 2013](lync-server-2013-database-software-support.md).

Sie sollten den SQL Server Cluster einrichten und konfigurieren, bevor Sie die Enterprise Edition-Front-End-Server und die Back-End-Datenbank installieren und bereitstellen. Bewährte Methoden und Setupanweisungen für die Failover-Clusterunterstützung in SQL Server 2012 finden Sie unter <https://technet.microsoft.com/library/hh231721.aspx> . Informationen zur Failover-Clusterunterstützung in SQL Server 2008 finden Sie unter <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .

Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.

<div>


> [!IMPORTANT]  
> Für die Installation und Bereitstellung der Datenbanken auf dem SQL Server-basierten Server müssen Sie Mitglied der SQL Server-Gruppe "sysadmin" für den SQL Server-basierten Server sein, auf dem die Datenbankdateien installiert werden. Wenn Sie kein Mitglied der SQL Server-Gruppe "sysadmin" sind, müssen Sie anfordern, dieser Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt wurden. Wenn Sie nicht zur Gruppe "sysadmin" hinzugefügt werden können, stellen Sie Ihrem SQL Server-Datenbankadministrator das Skript zur Konfiguration und Bereitstellung der Datenbanken bereit. Ausführliche Informationen zu den richtigen Benutzerrechten und-Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>So konfigurieren Sie das SQL Server-Clustering

1.  Nachdem Sie die Installation und Konfiguration von SQL Server Clustering abgeschlossen haben, definieren Sie den SQL Server Speicher im Topologie-Generator mithilfe des virtuellen Clusternamens SQL Server Instanz (wie im Setup für SQL Server Clustering konfiguriert) und dem Instanznamen der SQL Server Datenbank. Anders als bei einem einzelnen SQL Server-basierten Server verwenden Sie für einen geclusterten SQL Server-basierten Server den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des virtuellen Knotens.
    
    <div>
    

    > [!NOTE]  
    > Die einzelnen Windows Server-Clusterknoten müssen nicht für den Topologie-Generator konfiguriert werden. Sie verwenden ausschließlich den virtuellen SQL Server-Clusternamen.

    
    </div>

2.  Wenn Sie den Topologie-Generator zum Bereitstellen Ihrer Datenbanken verwenden, müssen Sie Mitglied der SQL Server sysadmin-Gruppe sein. Wenn Sie Mitglied der SQL Server sysadmin-Gruppe sind, aber keine Rechte in der Domäne haben (beispielsweise eine SQL Server-Datenbankadministrator Rolle), haben Sie die Berechtigung zum Erstellen der Datenbanken, aber nicht zum Lesen der erforderlichen Informationen in lync Server. Ausführliche Informationen zu den Benutzerrechten und-Berechtigungen, die für die Bereitstellung von lync Server erforderlich sind, finden Sie unter [Deployment Permissions for SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Stellen Sie mithilfe von SQL Server Management Studio sicher, dass die Standardordner für Datenbank und Protokolldateien den richtigen Datenträgerfreigaben im SQL Server-Cluster zugeordnet sind. Dieses Verfahren ist erforderlich, wenn Sie Datenbanken mit dem Topologie-Generator erstellen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie SQL Server Management Studio nicht installiert haben, können Sie die Installation nachholen, indem Sie die SQL Server-Installation erneut ausführen und das Verwaltungstool als zusätzliche Funktion für die vorhandene SQL Server-Bereitstellung auswählen.

    
    </div>

4.  Installieren Sie die Datenbanken für den SQL Server basierten Server entweder mithilfe des Topologie-Generators oder Windows PowerShell-Cmdlets. Verwenden Sie das folgende Verfahren, um den Topologie-Generator zu verwenden. Informationen zum Verwenden von Windows PowerShell-Cmdlets finden Sie unter [Database Installation using lync Server-Verwaltungsshell in lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>So erstellen Sie Datenbanken mithilfe des Topologie-Generators

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.
    
    <div>
    

    > [!WARNING]  
    > Im folgenden Verfahren wird davon ausgegangen, dass Sie Ihre Topologie im Topologie-Generator definiert und konfiguriert haben. Ausführliche Informationen zum Definieren Ihrer Topologie finden Sie unter<A href="lync-server-2013-defining-and-configuring-the-topology.md">definieren und Konfigurieren der Topologie in lync Server 2013</A>. Um mit dem Topologie-Generator die Topologie zu veröffentlichen und die Datenbank zu konfigurieren, müssen Sie als ein Benutzer mit den geeigneten Benutzerrechten und Gruppenmitgliedschaften angemeldet sein. Ausführliche Informationen zu den erforderlichen Rechten und Gruppenmitgliedschaften finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A>.

    
    </div>

2.  Klicken Sie beim Veröffentlichen der Topologie im Topologie-Generator auf der Seite **Datenbankenerstellen** auf **erweitert**.

3.  Auf der Seite **Speicherort für Datenbankdateien auswählen** stehen zwei Optionen zur Verfügung, mit denen festgelegt wird, wie Datenbankdateien im SQL Server-Cluster bereitgestellt werden. Wählen Sie eine der beiden Optionen aus:
    
      - **Ermitteln Sie automatisch den Speicherort der Datenbankdatei.** Diese Option verwendet einen Algorithmus zur Festlegung der Speicherorte für Datenbankprotokoll und Datendateien, basierend auf der Laufwerkkonfiguration auf dem SQL Server-basierten Server. Die Dateien werden so verteilt, dass eine optimale Leistung erzielt wird.
    
      - Standardpfade der SQL Server-Instanz verwenden. Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den SQL Server-Instanzeneinstellungen installiert. Nach Bereitstellung der Datenbankdateien auf dem SQL Server-basierten Server kann der SQL Server-Datenbankadministrator die Dateien an einen anderen Speicherort verschieben, um gemäß den jeweiligen SQL Server-Konfigurationsanforderungen die Leistung zu optimieren.

4.  Schließen Sie die Veröffentlichung der Topologie ab, und stellen Sie sicher, dass während des Vorgangs keine Fehler aufgetreten sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

