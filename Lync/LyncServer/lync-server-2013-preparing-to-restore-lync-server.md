---
title: 'Lync Server 2013: Vorbereiten der Wiederherstellung von lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Vorbereiten der Wiederherstellung von lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Bevor Sie mit dem Wiederherstellen von Servern und Datenbankennach einem Fehler beginnen, müssen Sie Folgendes ermitteln:

  - Was muss wiederhergestellt werden?

  - Die Hardware, Software, Daten und Tools, die Sie für die Wiederherstellung benötigen.

<div>

## <a name="determining-what-to-restore"></a>Bestimmen, was wiederhergestellt werden soll

In diesem Thema wird beschrieben, wie lync Server-Ausfälle wiederhergestellt werden, die auf der Ebene des Servers, Pools oder zentralen Verwaltungsspeichers auftreten. Wenn der zentrale Verwaltungsspeicher fehlschlägt, funktioniert Ihre lync Server-Bereitstellung weiterhin, aber Sie können keine Konfigurationsänderungen vornehmen. Wenn ein Back-End-Server oder Standard Edition-Server ausfällt, funktioniert der Benutzerpool nicht mehr. Wenn ein anderer Server ausfällt, hängt die Größe des Fehlers von der Serverrolle ab, die der Server ausführt, und davon, ob der Server mindestens eine Datenbank hostet.

### <a name="what-to-restore"></a>Was wiederhergestellt werden soll

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Wenn dies nicht möglich ist</th>
<th>Lesen Sie diesen Abschnitt:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition-Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>zentraler Verwaltungsspeicher</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet wird</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition-Back-End</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition, gespiegelt, primärer Back-End-Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition, gespiegelt, sekundärer Back-End-Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – Spiegelung</a></p></td>
</tr>
<tr class="even">
<td><p>Jeder Enterprise Edition-Server, auf dem eine Serverrolle ausgeführt wird, beispielsweise ein Front-End-Server, ein Edgeserver, Director, Mediation Server oder beständiger Chat Server.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ein ganzer lync Server-Pool</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Wiederherstellen eines lync Server-Pools in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition-Dateispeicher</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Wiederherstellen eines Dateispeichers in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Eine eigenständige Überwachungsdatenbank oder eine Archivierungsdatenbank</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Eine eigenständige Datenbank für beständigen Chat</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Wiederherstellen beständiger Chat-Daten in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Sammeln von Hardware, Software und Tools

Wenn Sie einen Server wiederherstellen, müssen Sie mit einem neuen oder sauberen Computer beginnen. Darüber hinaus müssen Sie die folgende Hardware und Software zur Verfügung haben:

  - Ein sauberer oder neuer Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie das Betriebssystem installieren, stellen Sie sicher, dass Sie das Computerkonto nicht in den Active Directory-Domänendiensten löschen, und überprüfen Sie, ob die Gruppen Berechtigungen für das Konto beibehalten werden.

    
    </div>

  - Installationssoftware für das Betriebssystem. Verwenden Sie zum Installieren des Betriebssystems die Server Bereitstellungsverfahren und-Konfigurationen, die von Ihrer Organisation eingerichtet wurden. Wenn Sie den Dienst wiederherstellen, sollten diese Verfahren und Konfigurationsanforderungen zur Verfügung stehen.

  - Installationssoftware für SQL Server 2012 oder SQL Server 2008 R2 Wenn Sie einen Datenbankserver installieren möchten, verwenden Sie die entsprechende Version von SQL Server und die von Ihrer Organisation eingerichteten Datenbankserver Bereitstellungsverfahren und-Konfigurationen. Wenn Sie den Dienst wiederherstellen, sollten diese Verfahren und Konfigurationsanforderungen zur Verfügung stehen.
    
    <div>
    

    > [!NOTE]  
    > Der lync Server-Bereitstellungs-Assistent installiert SQL Server 2012 Express auf jedem Standard Edition-Server und auf einem beliebigen anderen lync Server-Server automatisch, wenn ein lokaler Konfigurationsspeicher installiert ist, es sei denn, Sie haben SQL Server 2012 oder SQL Server 2008 R2 auf vorinstalliert. der Server.

    
    </div>

  - Software zum Aufnehmen von System Bildern.
    
    <div>
    

    > [!TIP]  
    > Wir empfehlen, dass Sie nach der Installation des Betriebssystems und SQL Server und vor dem Starten der Wiederherstellung eine Image-Kopie des Systems erstellen, damit Sie dieses Bild als Rollback-Point verwenden können, falls während der Wiederherstellung etwas schief geht.

    
    </div>

  - Lync Server 2013-Installationssoftware. Der lync Server-Bereitstellungs-Assistent befindet sich im lync Server-Installationsordner \\oder\\auf\\den Medien unter Setup amd64 Setup. exe.

Während der Wiederherstellung verwenden Sie die folgenden Tools:

  - Cmdlets der lync Server-Verwaltungsshell

  - Import-CsUserData

  - Tools zum Wiederherstellen von Windows-Ordnern

  - Topologie-Generator

  - SQL Server-Datenbankdienstprogramme wie SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Vorbereiten der Wiederherstellung eines Servers

Bevor Sie den Server wiederherstellen, müssen Sie die folgenden Schritte ausführen:

1.  Installieren Sie das Betriebssystem.

2.  Wenn es sich bei dem Server um einen Back-End-Server handelt, installieren Sie SQL Server 2012 oder SQL Server 2008 R2.

3.  Wiederherstellen oder Erneutes Registrieren Ihrer Zertifikate. Ausführliche Informationen zu Zertifikaten finden Sie unter "zusätzliche Sicherungsanforderungen" in den [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Erstellen Sie ein Abbild des Systems, bevor Sie die Wiederherstellung starten, um es als Rollback-Punkt zu verwenden, falls während der Wiederherstellung etwas schief geht.

<div>


> [!NOTE]  
> Den lync Server-Bereitstellungs-Assistenten und Cmdlets, die in den Vorgehensweisen in diesem Thema beschrieben sind, und Verwandte Themen, legen Sie alle erforderlichen Zugriffssteuerungslisten (ACLs) an.



</div>

Überprüfen Sie, ob die Hardware und die Software, die Sie für die Komponenten benötigen, die Sie wiederherstellen möchten, verfügbar sind, bevor Sie die Wiederherstellung starten. Nachdem Sie das Betriebssystem und SQL Server installiert haben, können die meisten Schritte in den folgenden Wiederherstellungsverfahren Remote ausgeführt werden. Die Ausnahmen sind in den Verfahren angegeben.

Außerdem sollten Sie den Sicherungs-und Wiederherstellungsplan Ihrer Organisation und die Informationen aus ihrer letzten Sicherung, wie etwa die Informationen in den Arbeitsblättern in diesem Dokument (Einzelheiten finden Sie unter [Sicherungs-und Wiederherstellungs Arbeitsblätter für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), angeben. verfügbar, bevor Sie mit der Wiederherstellung beginnen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

