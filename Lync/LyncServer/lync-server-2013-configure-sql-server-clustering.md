---
title: Konfigurieren von SQL Server-Clustering
TOCTitle: Konfigurieren von SQL Server-Clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56558907
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von SQL Server-Clustering

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync Server 2013 unterstützt Clustering für SQL Server 2012 und SQL Server 2008 R2. Ausführliche Informationen zu den Elementen, die unterstützt werden, finden Sie unter [Unterstützte Datenbanksoftware in Lync Server 2013](lync-server-2013-database-software-support.md).

Sie müssen den SQL Server-Cluster einrichten und konfigurieren, bevor Sie den Enterprise Edition-Front-End-Server sowie die Back-End-Datenbank installieren und bereitstellen. Bewährte Verfahren sowie Installationsanweisungen für Failoverclustering in SQL Server 2012 finden Sie unter <http://technet.microsoft.com/de-de/library/hh231721.aspx>. Informationen zum Failoverclustering in SQL Server 2008 finden Sie unter <http://technet.microsoft.com/de-de/library/ms189134(v=sql.105).aspx>.

Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.


> [!IMPORTANT]
> Für die Installation und Bereitstellung der Datenbanken auf dem SQL&nbsp;Server-basierten Server müssen Sie Mitglied der SQL&nbsp;Server-Gruppe "sysadmin" für den SQL&nbsp;Server-basierten Server sein, auf dem die Datenbankdateien installiert werden. Wenn Sie kein Mitglied der SQL&nbsp;Server-Gruppe "sysadmin" sind, müssen Sie anfordern, dieser Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt wurden. Wenn Sie nicht zur Gruppe "sysadmin" hinzugefügt werden können, stellen Sie Ihrem SQL&nbsp;Server-Datenbankadministrator das Skript zur Konfiguration und Bereitstellung der Datenbanken bereit. Ausführliche Informationen zu den erforderlichen Benutzerrechten und Berechtigungen zum Ausführen dieser Verfahren finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in Lync Server 2013</A>.



## So konfigurieren Sie das SQL Server-Clustering

1.  Nachdem Sie das SQL Server-Clustering installiert und konfiguriert haben, definieren Sie den SQL Server-Speicher im Topologie-Generator mit dem virtuellen Clusternamen der SQL Server-Instanz (wie konfiguriert beim Einrichten des SQL Server-Clusters) und dem Instanzennamen der SQL Server-Datenbank. Anders als bei einem einzelnen SQL Server-basierten Server verwenden Sie für einen geclusterten SQL Server-basierten Server den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des virtuellen Knotens.
    

    > [!NOTE]
    > Die einzelnen Windows Server-Clusterknoten müssen für den Topologie-Generator nicht konfiguriert werden. Sie verwenden ausschließlich den virtuellen SQL&nbsp;Server-Clusternamen.



2.  Wenn Sie die Datenbanken mit dem Topologie-Generator bereitstellen, müssen Sie Mitglied der SQL Server-Gruppe "sysadmin" sein. Wenn Sie Mitglied der Gruppe "sysadmin" in SQL Server sind, aber keine Berechtigungen in der Domäne innehaben (beispielsweise die Rolle des SQL Server-Datenbankadministrators), haben Sie zwar Rechte zum Erstellen der Datenbanken, können jedoch die erforderlichen Informationen in Lync Server nicht lesen. Ausführliche Informationen über die Benutzerrechte und Berechtigungen, die zum Bereitstellen von Lync Server benötigt werden, finden Sie unter [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Stellen Sie mithilfe von SQL Server Management Studio sicher, dass die Standardeinstellungen für Datenbankordner und Protokolldateienordner den richtigen Datenträgerfreigaben im SQL Server-Cluster zugeordnet sind. Dieses Verfahren ist erforderlich, wenn Sie Datenbanken mit dem Topologie-Generator erstellen.
    

    > [!NOTE]
    > Wenn Sie SQL Server Management Studio nicht installiert haben, können Sie die Installation nachholen, indem Sie die SQL&nbsp;Server-Installation erneut ausführen und das Verwaltungstool als zusätzliches Feature für die vorhandene SQL&nbsp;Server-Bereitstellung auswählen.



4.  Installieren Sie die Datenbanken für den SQL Server-basierten Server entweder mit dem Topologie-Generator oder mit Windows PowerShell-Cmdlets. Wenn Sie den Topologie-Generator verwenden, gehen Sie gemäß der nachstehenden Schrittfolge vor. Informationen zum Verwenden von Windows PowerShell-Cmdlets finden Sie unter [Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

## So erstellen Sie Datenbanken mit dem Topologie-Generator

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.
    

    > [!WARNING]
    > Bei dem folgenden Verfahren wird davon ausgegangen, dass Sie die Topologie im Topologie-Generator definiert und konfiguriert haben. Ausführliche Informationen zum Definieren einer Topologie finden Sie unter <A href="lync-server-2013-defining-and-configuring-the-topology.md">Definieren und Konfigurieren der Topologie in Lync Server 2013</A>. Um mit dem Topologie-Generator die Topologie zu veröffentlichen und die Datenbank zu konfigurieren, müssen Sie als ein Benutzer mit den geeigneten Benutzerrechten und Gruppenmitgliedschaften angemeldet sein. Ausführliche Informationen zu den erforderlichen Rechten und Gruppenmitgliedschaften finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in Lync Server 2013</A>.



2.  Klicken Sie im Topologie-Generator, wenn Sie die Topologie veröffentlichen, auf der Seite **Datenbanken erstellen** auf **Erweitert**.

3.  Auf der Seite **Speicherort für Datenbankdateien auswählen** stehen zwei Optionen zur Verfügung, mit denen festgelegt wird, wie Datenbankdateien im SQL Server-Cluster bereitgestellt werden. Wählen Sie eine der beiden Optionen aus:
    
      - **Speicherort für Datenbankdateien automatisch bestimmen**. Diese Option verwendet einen Algorithmus zur Festlegung der Speicherorte für Datenbankprotokoll und Datendateien, basierend auf der Laufwerkkonfiguration auf dem SQL Server-basierten Server. Die Dateien werden so verteilt, dass eine optimale Leistung erzielt wird.
    
      - Standardpfade der SQL Server-Instanz verwenden. Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den SQL Server-Instanzeneinstellungen installiert. Nach Bereitstellung der Datenbankdateien auf dem SQL Server-basierten Server kann der SQL Server-Datenbankadministrator die Dateien an einen anderen Speicherort verschieben, um gemäß den jeweiligen SQL Server-Konfigurationsanforderungen die Leistung zu optimieren.

4.  Schließen Sie die Veröffentlichung der Topologie ab, und vergewissern Sie sich, dass während des Vorgangs keine Fehler aufgetreten sind.

