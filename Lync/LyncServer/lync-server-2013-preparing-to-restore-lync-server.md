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

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="e4634-102">Vorbereiten der Wiederherstellung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4634-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4634-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e4634-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e4634-104">Bevor Sie mit dem Wiederherstellen von Servern und Datenbankennach einem Fehler beginnen, müssen Sie Folgendes ermitteln:</span><span class="sxs-lookup"><span data-stu-id="e4634-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="e4634-105">Was muss wiederhergestellt werden?</span><span class="sxs-lookup"><span data-stu-id="e4634-105">What needs to be restored.</span></span>

  - <span data-ttu-id="e4634-106">Die Hardware, Software, Daten und Tools, die Sie für die Wiederherstellung benötigen.</span><span class="sxs-lookup"><span data-stu-id="e4634-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="e4634-107">Bestimmen, was wiederhergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="e4634-107">Determining What to Restore</span></span>

<span data-ttu-id="e4634-108">In diesem Thema wird beschrieben, wie lync Server-Ausfälle wiederhergestellt werden, die auf der Ebene des Servers, Pools oder zentralen Verwaltungsspeichers auftreten.</span><span class="sxs-lookup"><span data-stu-id="e4634-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="e4634-109">Wenn der zentrale Verwaltungsspeicher fehlschlägt, funktioniert Ihre lync Server-Bereitstellung weiterhin, aber Sie können keine Konfigurationsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e4634-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="e4634-110">Wenn ein Back-End-Server oder Standard Edition-Server ausfällt, funktioniert der Benutzerpool nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="e4634-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="e4634-111">Wenn ein anderer Server ausfällt, hängt die Größe des Fehlers von der Serverrolle ab, die der Server ausführt, und davon, ob der Server mindestens eine Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="e4634-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="e4634-112">Was wiederhergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="e4634-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4634-113">Wenn dies nicht möglich ist</span><span class="sxs-lookup"><span data-stu-id="e4634-113">If this failed</span></span></th>
<th><span data-ttu-id="e4634-114">Lesen Sie diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="e4634-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4634-115">Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="e4634-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="e4634-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e4634-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4634-117">zentraler Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="e4634-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="e4634-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet wird</a></span><span class="sxs-lookup"><span data-stu-id="e4634-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4634-119">Enterprise Edition-Back-End</span><span class="sxs-lookup"><span data-stu-id="e4634-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="e4634-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e4634-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4634-121">Enterprise Edition, gespiegelt, primärer Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="e4634-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="e4634-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär</a></span><span class="sxs-lookup"><span data-stu-id="e4634-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4634-123">Enterprise Edition, gespiegelt, sekundärer Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="e4634-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="e4634-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – Spiegelung</a></span><span class="sxs-lookup"><span data-stu-id="e4634-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4634-125">Jeder Enterprise Edition-Server, auf dem eine Serverrolle ausgeführt wird, beispielsweise ein Front-End-Server, ein Edgeserver, Director, Mediation Server oder beständiger Chat Server.</span><span class="sxs-lookup"><span data-stu-id="e4634-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="e4634-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e4634-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4634-127">Ein ganzer lync Server-Pool</span><span class="sxs-lookup"><span data-stu-id="e4634-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="e4634-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Wiederherstellen eines lync Server-Pools in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e4634-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4634-129">Enterprise Edition-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="e4634-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="e4634-130"><a href="lync-server-2013-restoring-a-file-store.md">Wiederherstellen eines Dateispeichers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e4634-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4634-131">Eine eigenständige Überwachungsdatenbank oder eine Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="e4634-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="e4634-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e4634-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4634-133">Eine eigenständige Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="e4634-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="e4634-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Wiederherstellen beständiger Chat-Daten in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e4634-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="e4634-135">Sammeln von Hardware, Software und Tools</span><span class="sxs-lookup"><span data-stu-id="e4634-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="e4634-136">Wenn Sie einen Server wiederherstellen, müssen Sie mit einem neuen oder sauberen Computer beginnen.</span><span class="sxs-lookup"><span data-stu-id="e4634-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="e4634-137">Darüber hinaus müssen Sie die folgende Hardware und Software zur Verfügung haben:</span><span class="sxs-lookup"><span data-stu-id="e4634-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="e4634-138">Ein sauberer oder neuer Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Server.</span><span class="sxs-lookup"><span data-stu-id="e4634-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e4634-139">Wenn Sie das Betriebssystem installieren, stellen Sie sicher, dass Sie das Computerkonto nicht in den Active Directory-Domänendiensten löschen, und überprüfen Sie, ob die Gruppen Berechtigungen für das Konto beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="e4634-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="e4634-140">Installationssoftware für das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="e4634-140">Installation software for the operating system.</span></span> <span data-ttu-id="e4634-141">Verwenden Sie zum Installieren des Betriebssystems die Server Bereitstellungsverfahren und-Konfigurationen, die von Ihrer Organisation eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="e4634-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="e4634-142">Wenn Sie den Dienst wiederherstellen, sollten diese Verfahren und Konfigurationsanforderungen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e4634-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="e4634-143">Installationssoftware für SQL Server 2012 oder SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e4634-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="e4634-144">Wenn Sie einen Datenbankserver installieren möchten, verwenden Sie die entsprechende Version von SQL Server und die von Ihrer Organisation eingerichteten Datenbankserver Bereitstellungsverfahren und-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e4634-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="e4634-145">Wenn Sie den Dienst wiederherstellen, sollten diese Verfahren und Konfigurationsanforderungen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e4634-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4634-146">Der lync Server-Bereitstellungs-Assistent installiert SQL Server 2012 Express auf jedem Standard Edition-Server und auf einem beliebigen anderen lync Server-Server automatisch, wenn ein lokaler Konfigurationsspeicher installiert ist, es sei denn, Sie haben SQL Server 2012 oder SQL Server 2008 R2 auf vorinstalliert. der Server.</span><span class="sxs-lookup"><span data-stu-id="e4634-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="e4634-147">Software zum Aufnehmen von System Bildern.</span><span class="sxs-lookup"><span data-stu-id="e4634-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e4634-148">Wir empfehlen, dass Sie nach der Installation des Betriebssystems und SQL Server und vor dem Starten der Wiederherstellung eine Image-Kopie des Systems erstellen, damit Sie dieses Bild als Rollback-Point verwenden können, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="e4634-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="e4634-149">Lync Server 2013-Installationssoftware.</span><span class="sxs-lookup"><span data-stu-id="e4634-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="e4634-150">Der lync Server-Bereitstellungs-Assistent befindet sich im lync Server-Installationsordner \\oder\\auf\\den Medien unter Setup amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="e4634-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="e4634-151">Während der Wiederherstellung verwenden Sie die folgenden Tools:</span><span class="sxs-lookup"><span data-stu-id="e4634-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="e4634-152">Cmdlets der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="e4634-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="e4634-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="e4634-153">Import-CsUserData</span></span>

  - <span data-ttu-id="e4634-154">Tools zum Wiederherstellen von Windows-Ordnern</span><span class="sxs-lookup"><span data-stu-id="e4634-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="e4634-155">Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="e4634-155">Topology Builder</span></span>

  - <span data-ttu-id="e4634-156">SQL Server-Datenbankdienstprogramme wie SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e4634-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="e4634-157">Vorbereiten der Wiederherstellung eines Servers</span><span class="sxs-lookup"><span data-stu-id="e4634-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="e4634-158">Bevor Sie den Server wiederherstellen, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="e4634-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="e4634-159">Installieren Sie das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="e4634-159">Install the operating system.</span></span>

2.  <span data-ttu-id="e4634-160">Wenn es sich bei dem Server um einen Back-End-Server handelt, installieren Sie SQL Server 2012 oder SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e4634-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="e4634-161">Wiederherstellen oder Erneutes Registrieren Ihrer Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="e4634-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="e4634-162">Ausführliche Informationen zu Zertifikaten finden Sie unter "zusätzliche Sicherungsanforderungen" in den [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="e4634-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="e4634-163">Erstellen Sie ein Abbild des Systems, bevor Sie die Wiederherstellung starten, um es als Rollback-Punkt zu verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="e4634-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4634-164">Den lync Server-Bereitstellungs-Assistenten und Cmdlets, die in den Vorgehensweisen in diesem Thema beschrieben sind, und Verwandte Themen, legen Sie alle erforderlichen Zugriffssteuerungslisten (ACLs) an.</span><span class="sxs-lookup"><span data-stu-id="e4634-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="e4634-165">Überprüfen Sie, ob die Hardware und die Software, die Sie für die Komponenten benötigen, die Sie wiederherstellen möchten, verfügbar sind, bevor Sie die Wiederherstellung starten.</span><span class="sxs-lookup"><span data-stu-id="e4634-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="e4634-166">Nachdem Sie das Betriebssystem und SQL Server installiert haben, können die meisten Schritte in den folgenden Wiederherstellungsverfahren Remote ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e4634-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="e4634-167">Die Ausnahmen sind in den Verfahren angegeben.</span><span class="sxs-lookup"><span data-stu-id="e4634-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="e4634-168">Außerdem sollten Sie den Sicherungs-und Wiederherstellungsplan Ihrer Organisation und die Informationen aus ihrer letzten Sicherung, wie etwa die Informationen in den Arbeitsblättern in diesem Dokument (Einzelheiten finden Sie unter [Sicherungs-und Wiederherstellungs Arbeitsblätter für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), angeben. verfügbar, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="e4634-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

