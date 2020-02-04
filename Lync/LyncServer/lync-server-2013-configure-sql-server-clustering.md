---
title: 'Lync Server 2013: Konfigurieren des SQL Server-Clusters'
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
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Konfigurieren des SQL Server-Clusters für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-10_

Microsoft lync Server 2013 unterstützt Clustering für SQL Server 2012 und SQL Server 2008 R2. Details zu den unterstützten Informationen finden Sie unter [Unterstützung der Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md).

Sie sollten den SQL Server-Cluster einrichten und konfigurieren, bevor Sie den Enterprise Edition-Front-End-Server und die Back-End-Datenbank installieren und bereitstellen. Bewährte Methoden und Setupanweisungen für Failovercluster in SQL Server 2012 finden Sie unter <http://technet.microsoft.com/en-us/library/hh231721.aspx>. Informationen zum Failover-Clustering in SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>finden Sie unter.

Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.

<div>


> [!IMPORTANT]  
> Wenn Sie die Datenbanken auf dem SQL Server-basierten Server installieren und bereitstellen möchten, müssen Sie Mitglied der SQL Server sysadmin-Gruppe für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server-Gruppe sysadmin sind, müssen Sie die Gruppe so lange hinzufügen, bis die Datenbankdateien bereitgestellt sind. Wenn Sie nicht Mitglied der sysadmin-Gruppe werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen. Details zu den richtigen Benutzerrechten und Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>So konfigurieren Sie das SQL Server-Clustering

1.  Nachdem Sie die Installation und Konfiguration des SQL Server-Clusters abgeschlossen haben, definieren Sie den SQL Server-Speicher im Topologie-Generator mithilfe des virtuellen Clusternamens der SQL Server-Instanz (wie im Setup für SQL Server-Clustering konfiguriert) und der Instanz. der Name der SQL Server-Datenbank. Anders als ein einzelner SQL Server-basierter Server verwenden Sie den virtuellen Knoten vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für einen gruppierten SQL Server-basierten Server.
    
    <div>
    

    > [!NOTE]  
    > Die einzelnen Windows Server-Clusterknoten müssen nicht für den Topologie-Generator konfiguriert werden. Sie verwenden nur den virtuellen SQL Server-Clusternamen.

    
    </div>

2.  Wenn Sie die Datenbanken mithilfe des Topologie-Generators bereitstellen, müssen Sie Mitglied der SQL Server-Gruppe sysadmin sein. Wenn Sie ein Mitglied der SQL Server sysadmin-Gruppe sind, aber nicht über Berechtigungen in der Domäne (beispielsweise eine SQL Server-Datenbankadministrator Rolle) verfügen, verfügen Sie über die Rechte zum Erstellen der Datenbanken, aber nicht zum Lesen der erforderlichen Informationen in lync Server. Details zu den Benutzerrechten und Berechtigungen, die für die Bereitstellung von lync Server erforderlich sind, finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Stellen Sie sicher, dass die Standardeinstellungen für den Ordner "Datenbank" und "Protokolldateien" den freigegebenen Datenträgern im SQL Server-Cluster mithilfe von SQL Server Management Studio ordnungsgemäß zugeordnet sind. Dies ist ein erforderliches Verfahren, wenn Sie Datenbanken mithilfe des Topologie-Generators erstellen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie SQL Server Management Studio nicht installiert haben, können Sie es installieren, indem Sie die SQL Server-Installation erneut ausführen und dann das Verwaltungstool als hinzugefügtes Feature für die vorhandene SQL Server-Bereitstellung auswählen.

    
    </div>

4.  Installieren Sie die Datenbanken für den SQL Server-basierten Server mithilfe von Topology Builder oder Windows PowerShell-Cmdlets. Gehen Sie wie folgt vor, um den Topologie-Generator zu verwenden: Informationen zum Verwenden von Windows PowerShell-Cmdlets finden Sie unter [Datenbankinstallation mithilfe der lync Server-Verwaltungsshell in lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>So erstellen Sie Datenbanken mit dem Topologie-Generator

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.
    
    <div>
    

    > [!WARNING]  
    > Im folgenden Verfahren wird davon ausgegangen, dass Sie Ihre Topologie im Topologie-Generator definiert und konfiguriert haben. Details zum Definieren Ihrer Topologie finden Sie unter<A href="lync-server-2013-defining-and-configuring-the-topology.md">definieren und Konfigurieren der Topologie in lync Server 2013</A>. Wenn Sie die Topologie mithilfe des Topologie-Generators veröffentlichen und die Datenbank konfigurieren möchten, müssen Sie sich als Benutzer mit den richtigen Benutzerrechten und Gruppenmitgliedschaften anmelden. Details zu den erforderlichen Berechtigungen und Gruppenmitgliedschaften finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</A>.

    
    </div>

2.  Klicken Sie im Topologie-Generator während der Veröffentlichung der Topologie auf der Seite **Datenbankenerstellen** auf **erweitert**.

3.  Auf der Seite " **Speicherort der Datenbankdatei auswählen** " gibt es zwei Optionen, die bestimmen, wie die Datenbankdateien im SQL Server-Cluster bereitgestellt werden. Wählen Sie eine der folgenden Optionen aus:
    
      - **Ermitteln Sie den Speicherort der Datenbankdatei automatisch.** Bei dieser Auswahl wird ein Algorithmus verwendet, um das Datenbankprotokoll und die Speicherorte der Datendateien basierend auf der Laufwerkskonfiguration auf dem auf SQL Server basierenden Server zu ermitteln. Die Dateien werden so verteilt, dass Sie versuchen, eine optimale Leistung zu erzielen.
    
      - Verwenden Sie die Standardeinstellungen für SQL Server-Instanzen. Wenn Sie diese Option auswählen, werden die Protokoll-und Datendateien entsprechend den SQL Server-Instanzen Einstellungen installiert. Nach der Bereitstellung der Datenbankdateien auf dem SQL Server kann der SQL Server-Datenbankadministrator die Dateien möglicherweise verschieben, um die Leistung für Ihre speziellen SQL Server-Konfigurationsanforderungen zu optimieren.

4.  Führen Sie die Veröffentlichung der Topologie aus, und vergewissern Sie sich, dass während des Vorgangs keine Fehler aufgetreten sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

