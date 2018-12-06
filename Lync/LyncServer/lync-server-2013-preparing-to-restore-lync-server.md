---
title: Vorbereiten der Wiederherstellung von Lync Server
TOCTitle: Vorbereiten der Wiederherstellung von Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202179(v=OCS.15)
ms:contentKeyID: 52056395
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten der Wiederherstellung von Lync Server

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Sie müssen Folgendes bestimmen, bevor Sie nach einem aufgetretenen Fehler mit dem Wiederherstellen von Servern und Datenbanken beginnen:

  - Was wiederhergestellt werden muss

  - Die für die Wiederherstellung benötigte(n) Hardware, Software, Daten und Tools

## Bestimmen der wiederherzustellenden Komponenten

In diesem Thema wird die Wiederherstellung von Lync Server nach Ausfällen auf der Ebene der Server, Pools oder des zentralen Verwaltungsspeichers beschrieben. Wenn ein Fehler beim zentralen Verwaltungsspeicher auftritt, ist die Lync Server-Bereitstellung weiterhin funktionsfähig, allerdings können Sie keine Konfigurationsänderungen vornehmen. Falls bei einem Back-End-Server oder Standard Edition-Server ein Fehler auftritt, ist der Benutzerpool nicht mehr funktionsfähig. Falls bei irgendeinem anderen Server ein Fehler auftritt, ist das Ausmaß des Fehlers abhängig von der Serverrolle sowie der Tatsache, ob von dem Server eine oder mehrere Datenbanken gehostet werden.

### Wiederherzustellende Komponenten

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bei einem Fehler dieser Komponente:</th>
<th>Siehe diesen Abschnitt:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition-Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers</a></p></td>
</tr>
<tr class="even">
<td><p>zentralen Verwaltungsspeicher</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet</a></p></td>
</tr>
<tr class="odd">
<td><p>Back-End-Server der Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Back-End-Servers der Enterprise Edition</a></p></td>
</tr>
<tr class="even">
<td><p>Gespiegelter primärer Back-End-Server der Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Primär</a></p></td>
</tr>
<tr class="odd">
<td><p>Gespiegelter sekundärer Back-End-Server der Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegel</a></p></td>
</tr>
<tr class="even">
<td><p>Ein beliebiger Enterprise Edition-Server, der mit einer Serverrolle ausgeführt wird, wie z. B. Front-End-Server, Edgeserver, Director, Vermittlungsserver oder ein Server für beständigen Chat.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers</a></p></td>
</tr>
<tr class="odd">
<td><p>Ein kompletter Lync Server-Pool</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Wiederherstellen eines Lync Server-Pools</a></p></td>
</tr>
<tr class="even">
<td><p>Dateispeicher der Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Wiederherstellen eines Dateispeichers</a></p></td>
</tr>
<tr class="odd">
<td><p>Eine eigenständige Überwachungs- oder Archvierungsdatenbank</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Wiederherstellen von Überwachungs- oder Archivierungsdaten</a></p></td>
</tr>
<tr class="even">
<td><p>Eine eigenständige Datenbank für beständigen Chat</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Wiederherstellen von Daten des beständigen Chats</a></p></td>
</tr>
</tbody>
</table>


## Zusammenstellen der Hardware, Software und Tools

Beim Wiederherstellen eines Servers müssen Sie mit einem neuen oder neu formatierten Computer beginnen. Zudem sollte folgende Hardware und Software verfügbar sein:

  - Ein neu formatierter oder neuer Server mit demselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Server.
    

    > [!IMPORTANT]
    > Achten Sie beim Installieren des Betriebssystems darauf, dass Sie das Computerkonto in Active Directory-Domänendienste nicht löschen, und stellen Sie sicher, dass die Gruppenberechtigungen für das Konto beibehalten werden.



  - Installationssoftware für das Betriebssystem. Verwenden Sie zum Installieren des Betriebssystems die Verfahren und Konfigurationen Ihrer Organisation für die Serverbereitstellung. Sie sollten diese Verfahren und Konfigurationsanforderungen zur Hand haben, wenn Sie die Bereitschaft des Servers wiederherstellen.

  - Installationssoftware für SQL Server 2012 oder SQL Server 2008 R2. Verwenden Sie zum Installieren eines Datenbankservers die entsprechende SQL Server-Version sowie die Verfahren und Konfigurationen Ihrer Organisation für die Datenbankserverbereitstellung. Sie sollten diese Verfahren und Konfigurationsanforderungen zur Hand haben, wenn Sie die Bereitschaft des Servers wiederherstellen.
    

    > [!NOTE]
    > Mit dem Lync Server-Bereitstellungs-Assistenten wird SQL&nbsp;Server&nbsp;2012&nbsp;Express automatisch auf jedem Standard Edition-Server und auf jedem anderen Lync Server-Server installiert, wenn ein lokaler Konfigurationsspeicher installiert wird, es sei denn, Sie haben SQL&nbsp;Server&nbsp;2012 oder SQL&nbsp;Server&nbsp;2008&nbsp;R2 auf dem Server vorinstalliert.



  - Software zum Erstellen von Systemimages.
    

    > [!TIP]
    > Es wird empfohlen, ein Systemimage zu erstellen, nachdem Sie das Betriebssystem und SQL&nbsp;Server installiert haben und bevor Sie mit der Wiederherstellung beginnen. Sollte bei der Wiederherstellung etwas schief gehen, können Sie dann mithilfe dieses Images ein Rollback ausführen.



  - Lync Server 2013-Installationssoftware. Der Lync Server-Bereitstellungs-Assistent befindet sich im Lync Server-Installationsordner oder auf dem Medium im Verzeichnis **\\setup\\amd64\\Setup.exe**.

Während der Wiederherstellung verwenden Sie die folgenden Tools:

  - Lync Server-Verwaltungsshell-Cmdlets

  - Import-CsUserData

  - Tools zum Wiederherstellen von Windows-Ordnern

  - Topologie-Generator

  - SQL Server-Datenbankhilfsprogramme wie z. B. SQL Server Management Studio

## Vorbereitungen für die Wiederherstellung eines Servers

Vor der Wiederherstellung des Servers müssen Sie die folgenden Schritte ausführen:

1.  Installieren Sie das Betriebssystem.

2.  Falls es sich beim Server um einen Back-End-Server handelt, installieren Sie SQL Server 2012 oder SQL Server 2008 R2.

3.  Stellen Sie Ihre Zertifikate wieder her, oder registrieren Sie sie erneut. Ausführliche Informationen finden unter "Zusätzliche Sicherungsanforderungen" in [Anforderungen für die Sicherung und Wiederherstellung: Daten](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Erstellen Sie ein Image des Systems, bevor Sie mit der Wiederherstellung beginnen. Sollte bei der Wiederherstellung etwas schief gehen, können Sie dann mithilfe dieses Images ein Rollback ausführen.


> [!NOTE]
> Mit dem Lync Server-Bereitstellungs-Assistenten und den in den Verfahren in diesem Thema sowie in verwandten Themen beschriebenen Cmdlets werden alle erforderlichen Zugriffsteuerungslisten (Access Control Lists, ACLs) festgelegt.



Stellen Sie sicher, dass die Hardware und Software, die Sie für die wiederherzustellenden Komponenten benötigen, verfügbar ist, bevor Sie mit der Wiederherstellung beginnen. Nachdem Sie das Betriebssystem und SQL Server installiert haben, können die meisten Schritte in den folgenden Wiederherstellungsverfahren remote ausgeführt werden. In den Verfahren wird auf die Ausnahmen hingewiesen.

Darüber hinaus sollten der Sicherungs- und Wiederherstellungsplan Ihrer Organisation sowie die Informationen der letzten Sicherung, wie z. B. die Informationen aus den Arbeitsblättern in diesem Dokument (ausführliche Informationen finden Sie unter [Arbeitsblätter zur Sicherung und Wiederherstellung](lync-server-2013-backup-and-restoration-worksheets.md)) verfügbar sein, bevor Sie mit der Wiederherstellung beginnen.

