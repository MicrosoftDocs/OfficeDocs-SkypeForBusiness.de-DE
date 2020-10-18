---
title: 'Lync Server 2013: Vorbereiten der Wiederherstellung lync Server'
description: 'Lync Server 2013: Vorbereiten der Wiederherstellung lync Server.'
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
ms.openlocfilehash: 1875a691cfb70a6a824ab19bfde3dee4d699e48a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579951"
---
# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="c6a57-103">Vorbereiten der Wiederherstellung lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6a57-103">Preparing to restore Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6a57-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c6a57-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c6a57-105">Sie müssen Folgendes bestimmen, bevor Sie nach einem aufgetretenen Fehler mit dem Wiederherstellen von Servern und Datenbanken beginnen:</span><span class="sxs-lookup"><span data-stu-id="c6a57-105">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="c6a57-106">Was muss wiederhergestellt werden?</span><span class="sxs-lookup"><span data-stu-id="c6a57-106">What needs to be restored.</span></span>

  - <span data-ttu-id="c6a57-107">Die Hardware, Software, Daten und Tools, die Sie für die Wiederherstellung benötigen.</span><span class="sxs-lookup"><span data-stu-id="c6a57-107">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="c6a57-108">Bestimmen der wiederherzustellenden Komponenten</span><span class="sxs-lookup"><span data-stu-id="c6a57-108">Determining What to Restore</span></span>

<span data-ttu-id="c6a57-109">In diesem Thema wird beschrieben, wie Sie lync Server Ausfälle wiederherstellen, die auf der Ebene des Servers, des Pools oder des zentralen Verwaltungsspeichers auftreten.</span><span class="sxs-lookup"><span data-stu-id="c6a57-109">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="c6a57-110">Wenn der zentrale Verwaltungsspeicher fehlschlägt, funktioniert Ihre lync Server-Bereitstellung weiterhin, aber Sie können keine Konfigurationsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c6a57-110">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="c6a57-111">Wenn ein Back-End-Server oder Standard Edition-Server Fehler auftritt, wird der Benutzerpool nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="c6a57-111">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="c6a57-112">Wenn ein anderer Server ausfällt, hängt die Größe des Fehlers von der Serverrolle ab, auf der der Server ausgeführt wird, und davon, ob der Server mindestens eine Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="c6a57-112">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="c6a57-113">Wiederherzustellende Komponenten</span><span class="sxs-lookup"><span data-stu-id="c6a57-113">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6a57-114">Bei einem Fehler dieser Komponente:</span><span class="sxs-lookup"><span data-stu-id="c6a57-114">If this failed</span></span></th>
<th><span data-ttu-id="c6a57-115">Siehe diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="c6a57-115">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6a57-116">Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="c6a57-116">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c6a57-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a57-118">zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="c6a57-118">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="c6a57-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a57-120">Enterprise Edition-Back-End</span><span class="sxs-lookup"><span data-stu-id="c6a57-120">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="c6a57-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a57-122">Enterprise Edition-gespiegelter Back-End-primärer Server</span><span class="sxs-lookup"><span data-stu-id="c6a57-122">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="c6a57-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a57-124">Enterprise Edition-gespiegelte Back-End-sekundären Server</span><span class="sxs-lookup"><span data-stu-id="c6a57-124">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="c6a57-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a57-126">Jede Enterprise Edition-Server, die eine Serverrolle ausführt, beispielsweise eine Front-End-Server, Edgeserver, Director, Vermittlungsserver oder persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="c6a57-126">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="c6a57-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a57-128">Gesamter lync Server Pool</span><span class="sxs-lookup"><span data-stu-id="c6a57-128">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="c6a57-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Wiederherstellen eines lync Server Pools in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a57-130">Enterprise Edition-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="c6a57-130">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="c6a57-131"><a href="lync-server-2013-restoring-a-file-store.md">Wiederherstellen eines Dateispeichers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-131"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a57-132">Ein eigenständiges Überwachungsdatenbank oder Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="c6a57-132">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="c6a57-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a57-134">Eine eigenständige Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="c6a57-134">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="c6a57-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Wiederherstellen von Daten für beständigen Chat in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c6a57-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="c6a57-136">Zusammenstellen der Hardware, Software und Tools</span><span class="sxs-lookup"><span data-stu-id="c6a57-136">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="c6a57-137">Beim Wiederherstellen eines Servers müssen Sie mit einem neuen oder neu formatierten Computer beginnen.</span><span class="sxs-lookup"><span data-stu-id="c6a57-137">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="c6a57-138">Darüber hinaus benötigen Sie die folgende Hardware und Software zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c6a57-138">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="c6a57-139">Ein neu formatierter oder neuer Server mit demselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Server.</span><span class="sxs-lookup"><span data-stu-id="c6a57-139">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c6a57-140">Wenn Sie das Betriebssystem installieren, stellen Sie sicher, dass Sie das Computerkonto nicht in Active Directory-Domänendienste löschen, und vergewissern Sie sich, dass die Gruppen Berechtigungen für das Konto beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c6a57-140">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="c6a57-141">Installationssoftware für das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c6a57-141">Installation software for the operating system.</span></span> <span data-ttu-id="c6a57-142">Verwenden Sie zum Installieren des Betriebssystem die Verfahren und Konfigurationen Ihrer Organisation für die Serverbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="c6a57-142">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="c6a57-143">Diese Verfahren und Konfigurationsanforderungen sollten beim Wiederherstellen des Diensts verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="c6a57-143">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="c6a57-144">Installationssoftware für SQL Server 2012 oder SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="c6a57-144">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="c6a57-145">Verwenden Sie zum Installieren eines Datenbankservers die entsprechende SQL Server-Version sowie die Verfahren und Konfigurationen Ihrer Organisation für die Datenbankserverbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="c6a57-145">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="c6a57-146">Diese Verfahren und Konfigurationsanforderungen sollten beim Wiederherstellen des Diensts verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="c6a57-146">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6a57-147">Der Assistent für die lync Server-Bereitstellung installiert SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und auf einem anderen lync Server Server, wenn ein lokaler Konfigurationsspeicher installiert ist, es sei denn, Sie haben SQL Server 2012 oder SQL Server 2008 R2 auf dem Server vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="c6a57-147">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="c6a57-148">Software zum Erstellen von Systemimages.</span><span class="sxs-lookup"><span data-stu-id="c6a57-148">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c6a57-149">Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, nachdem Sie das Betriebssystem und die SQL Server installiert haben, und bevor Sie die Wiederherstellung starten, damit Sie dieses Bild als Rollback-Punkt verwenden können, falls bei der Wiederherstellung ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c6a57-149">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="c6a57-150">Lync Server 2013 Installationssoftware.</span><span class="sxs-lookup"><span data-stu-id="c6a57-150">Lync Server 2013 installation software.</span></span> <span data-ttu-id="c6a57-151">Der lync Server-Bereitstellungs-Assistent befindet sich im lync Server Installationsordner oder auf dem Medium \\ Setup \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="c6a57-151">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="c6a57-152">Während der Wiederherstellung verwenden Sie die folgenden Tools:</span><span class="sxs-lookup"><span data-stu-id="c6a57-152">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="c6a57-153">Lync Server-Verwaltungsshell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c6a57-153">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="c6a57-154">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="c6a57-154">Import-CsUserData</span></span>

  - <span data-ttu-id="c6a57-155">Tools zum Wiederherstellen von Windows-Ordnern</span><span class="sxs-lookup"><span data-stu-id="c6a57-155">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="c6a57-156">Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="c6a57-156">Topology Builder</span></span>

  - <span data-ttu-id="c6a57-157">SQL Server-Datenbankhilfsprogramme wie z. B. SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6a57-157">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="c6a57-158">Vorbereitungen für die Wiederherstellung eines Servers</span><span class="sxs-lookup"><span data-stu-id="c6a57-158">Preparing to Restore a Server</span></span>

<span data-ttu-id="c6a57-159">Bevor Sie den Server wiederherstellen, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c6a57-159">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="c6a57-160">Installieren Sie das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c6a57-160">Install the operating system.</span></span>

2.  <span data-ttu-id="c6a57-161">Wenn es sich bei dem Server um einen Back-End-Server handelt, installieren Sie SQL Server 2012 oder SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="c6a57-161">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="c6a57-162">Stellen Sie Ihre Zertifikate wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="c6a57-162">Restore or reenroll your certificates.</span></span> <span data-ttu-id="c6a57-163">Ausführliche Informationen zu Zertifikaten finden Sie unter "Additional Backup Requirements" in [Backup and Recovery Requirements in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="c6a57-163">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="c6a57-164">Erstellen Sie ein Abbild des Systems, bevor Sie die Wiederherstellung als Rollback-Punkt verwenden, falls während der Wiederherstellung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="c6a57-164">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6a57-165">Mit dem lync Server-Bereitstellungs-Assistenten und den in den Verfahren in diesem Thema und verwandten Themen beschriebenen Cmdlets werden alle erforderlichen Zugriffssteuerungslisten (Access Control Lists, ACLs) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c6a57-165">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="c6a57-166">Stellen Sie sicher, dass die Hardware und die Software, die Sie für die wiederherzustellenden Komponenten benötigen, verfügbar sind, bevor Sie die Wiederherstellung starten.</span><span class="sxs-lookup"><span data-stu-id="c6a57-166">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="c6a57-167">Nachdem Sie das Betriebssystem und SQL Server installiert haben, können die meisten Schritte in den folgenden Wiederherstellungsverfahren remote ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c6a57-167">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="c6a57-168">In den Verfahren wird auf die Ausnahmen hingewiesen.</span><span class="sxs-lookup"><span data-stu-id="c6a57-168">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="c6a57-169">Sie sollten auch den Sicherungs-und Wiederherstellungsplan Ihrer Organisation und die Informationen aus der letzten Sicherung haben, beispielsweise die Informationen in den Arbeitsblättern in diesem Dokument (Ausführliche Informationen finden Sie unter [Sicherungs-und Wiederherstellungs Arbeitsblätter für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), die verfügbar sind, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="c6a57-169">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

