---
title: 'Lync Server 2013: Vorbereiten der Wiederherstellung lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd5875dc7e0dd999a1d94e6e7722eeba07c3a37e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Vorbereiten der Wiederherstellung lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Sie müssen Folgendes bestimmen, bevor Sie nach einem aufgetretenen Fehler mit dem Wiederherstellen von Servern und Datenbanken beginnen:

  - Was muss wiederhergestellt werden?

  - Die Hardware, Software, Daten und Tools, die Sie für die Wiederherstellung benötigen.

<div>

## <a name="determining-what-to-restore"></a>Bestimmen der wiederherzustellenden Komponenten

In diesem Thema wird beschrieben, wie Sie lync Server Ausfälle wiederherstellen, die auf der Ebene des Servers, des Pools oder des zentralen Verwaltungsspeichers auftreten. Wenn der zentrale Verwaltungsspeicher fehlschlägt, funktioniert Ihre lync Server-Bereitstellung weiterhin, aber Sie können keine Konfigurationsänderungen vornehmen. Wenn ein Back-End-Server oder Standard Edition-Server Fehler auftritt, wird der Benutzerpool nicht mehr funktionsfähig. Wenn ein anderer Server ausfällt, hängt die Größe des Fehlers von der Serverrolle ab, auf der der Server ausgeführt wird, und davon, ob der Server mindestens eine Datenbank hostet.

### <a name="what-to-restore"></a>Wiederherzustellende Komponenten

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
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>zentralen Verwaltungsspeicher</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition-Back-End</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition-gespiegelter Back-End-primärer Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition-gespiegelte Back-End-sekundären Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Jede Enterprise Edition-Server, die eine Serverrolle ausführt, beispielsweise eine Front-End-Server, Edgeserver, Director, Vermittlungsserver oder persistent Chat Server.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Gesamter lync Server Pool</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Wiederherstellen eines lync Server Pools in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition-Dateispeicher</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Wiederherstellen eines Dateispeichers in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ein eigenständiges Überwachungsdatenbank oder Archivierungsdatenbank</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Eine eigenständige Datenbank für beständigen Chat</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Wiederherstellen von Daten für beständigen Chat in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Zusammenstellen der Hardware, Software und Tools

Beim Wiederherstellen eines Servers müssen Sie mit einem neuen oder neu formatierten Computer beginnen. Darüber hinaus benötigen Sie die folgende Hardware und Software zur Verfügung:

  - Ein neu formatierter oder neuer Server mit demselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie das Betriebssystem installieren, stellen Sie sicher, dass Sie das Computerkonto nicht in Active Directory-Domänendienste löschen, und vergewissern Sie sich, dass die Gruppen Berechtigungen für das Konto beibehalten werden.

    
    </div>

  - Installationssoftware für das Betriebssystem. Verwenden Sie zum Installieren des Betriebssystem die Verfahren und Konfigurationen Ihrer Organisation für die Serverbereitstellung. Diese Verfahren und Konfigurationsanforderungen sollten beim Wiederherstellen des Diensts verfügbar sein.

  - Installationssoftware für SQL Server 2012 oder SQL Server 2008 R2. Verwenden Sie zum Installieren eines Datenbankservers die entsprechende SQL Server-Version sowie die Verfahren und Konfigurationen Ihrer Organisation für die Datenbankserverbereitstellung. Diese Verfahren und Konfigurationsanforderungen sollten beim Wiederherstellen des Diensts verfügbar sein.
    
    <div>
    

    > [!NOTE]  
    > Der Assistent für die lync Server-Bereitstellung installiert SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und auf einem anderen lync Server Server, wenn ein lokaler Konfigurationsspeicher installiert ist, es sei denn, Sie haben SQL Server 2012 oder SQL Server 2008 R2 vorinstalliert. dem Server.

    
    </div>

  - Software zum Erstellen von Systemimages.
    
    <div>
    

    > [!TIP]  
    > Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, nachdem Sie das Betriebssystem und die SQL Server installiert haben, und bevor Sie die Wiederherstellung starten, damit Sie dieses Bild als Rollback-Punkt verwenden können, falls bei der Wiederherstellung ein Fehler aufgetreten ist.

    
    </div>

  - Lync Server 2013 Installationssoftware. Der lync Server-Bereitstellungs-Assistent befindet sich im lync Server Installationsordner oder \\auf\\dem\\Medium unter Setup amd64 Setup. exe.

Während der Wiederherstellung verwenden Sie die folgenden Tools:

  - Lync Server-Verwaltungsshell-Cmdlets

  - Import-csuserdata "

  - Tools zum Wiederherstellen von Windows-Ordnern

  - Topologie-Generator

  - SQL Server-Datenbankhilfsprogramme wie z. B. SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Vorbereitungen für die Wiederherstellung eines Servers

Bevor Sie den Server wiederherstellen, müssen Sie die folgenden Schritte ausführen:

1.  Installieren Sie das Betriebssystem.

2.  Wenn es sich bei dem Server um einen Back-End-Server handelt, installieren Sie SQL Server 2012 oder SQL Server 2008 R2.

3.  Stellen Sie Ihre Zertifikate wieder her oder registrieren Sie Sie erneut. Ausführliche Informationen zu Zertifikaten finden Sie unter "Additional Backup Requirements" in [Backup and Recovery Requirements in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Erstellen Sie ein Abbild des Systems, bevor Sie die Wiederherstellung als Rollback-Punkt verwenden, falls während der Wiederherstellung ein Fehler auftritt.

<div>


> [!NOTE]  
> Mit dem lync Server-Bereitstellungs-Assistenten und den in den Verfahren in diesem Thema und verwandten Themen beschriebenen Cmdlets werden alle erforderlichen Zugriffssteuerungslisten (Access Control Lists, ACLs) festgelegt.



</div>

Stellen Sie sicher, dass die Hardware und die Software, die Sie für die wiederherzustellenden Komponenten benötigen, verfügbar sind, bevor Sie die Wiederherstellung starten. Nachdem Sie das Betriebssystem und SQL Server installiert haben, können die meisten Schritte in den folgenden Wiederherstellungsverfahren remote ausgeführt werden. In den Verfahren wird auf die Ausnahmen hingewiesen.

Sie sollten auch den Sicherungs-und Wiederherstellungsplan Ihrer Organisation und die Informationen aus der letzten Sicherung haben, beispielsweise die Informationen in den Arbeitsblättern in diesem Dokument (Ausführliche Informationen finden Sie unter [Sicherungs-und Wiederherstellungs Arbeitsblätter für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), die verfügbar sind, bevor Sie mit der Wiederherstellung beginnen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

