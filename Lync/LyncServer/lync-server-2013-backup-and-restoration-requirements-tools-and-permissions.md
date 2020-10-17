---
title: 'Lync Server 2013: Anforderungen an die Sicherung und Wiederherstellung: Tools und Berechtigungen'
description: 'Lync Server 2013: Anforderungen an die Sicherung und Wiederherstellung: Tools und Berechtigungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553467"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="ca8da-103">Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ca8da-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca8da-104">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="ca8da-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="ca8da-105">In diesem Thema werden die Tools beschrieben, die Sie zum Sichern und Wiederherstellen von lync Server 2013, den benötigten Berechtigungen und zum Remote-oder lokalen Ausführen von Befehlen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ca8da-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="ca8da-106">Dieses Thema konzentriert sich insbesondere auf Tools, die mit lync Server für Sicherung und Wiederherstellung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="ca8da-107">Sicherungen</span><span class="sxs-lookup"><span data-stu-id="ca8da-107">Backups</span></span>

<span data-ttu-id="ca8da-108">Verwenden Sie die in der folgenden Tabelle aufgeführten Tools, um lync Server zu sichern.</span><span class="sxs-lookup"><span data-stu-id="ca8da-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="ca8da-109">Alle Befehle, die Sie zum Sichern von lync Server benötigen, können mit einem Skript erstellt werden und können Remote ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="ca8da-110">Tools zum Sichern von lync Server</span><span class="sxs-lookup"><span data-stu-id="ca8da-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca8da-111">Zu sichern:</span><span class="sxs-lookup"><span data-stu-id="ca8da-111">To back up this:</span></span></th>
<th><span data-ttu-id="ca8da-112">Zu verwendendes Tool oder Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ca8da-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-113">Topologiekonfigurationsdaten (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca8da-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-115">Daten zum Standortinformationsdienst (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca8da-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-117">Reaktionsgruppen-Konfigurationsdaten (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca8da-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-119">Persistente Benutzerdaten ("rtcxds". mdf-Datenbank)</span><span class="sxs-lookup"><span data-stu-id="ca8da-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="ca8da-120">Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="ca8da-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="ca8da-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="ca8da-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="ca8da-122">Archivierungsdatenbank (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="ca8da-123">Überwachungsdatenbank zu Kommunikationsdatensätzen (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="ca8da-124">QoE-Überwachungsdatenbank (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ca8da-125">SQL Server-Datenbanktool, z. B. SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ca8da-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-126">Datenbank für beständigen Chat (MGC. mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-127">SQL Server Sicherungsverfahren oder Export-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="ca8da-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="ca8da-128">Export-CsPersistentChatData exportiert persistent Chat-Daten als Datei.</span><span class="sxs-lookup"><span data-stu-id="ca8da-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-129">Alle Dateispeicher: lync Server Dateispeicher, archivieren des Dateispeichers</span><span class="sxs-lookup"><span data-stu-id="ca8da-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ca8da-130">Dateien mit dem Namen <STRONG>Meeting.Active</STRONG> sollten nicht gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="ca8da-131">Diese Dateien sind während Besprechungen in Gebrauch und daher gesperrt.</span><span class="sxs-lookup"><span data-stu-id="ca8da-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="ca8da-132">Standard mäßiges Dateisystem-Verwaltungstool wie Robocopy.</span><span class="sxs-lookup"><span data-stu-id="ca8da-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="ca8da-133">Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="ca8da-133">Restoration</span></span>

<span data-ttu-id="ca8da-134">Verwenden Sie die in der folgenden Tabelle aufgeführten Tools, um lync Server wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ca8da-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="ca8da-135">Alle Befehle, die Sie zum Wiederherstellen von lync Server benötigen, können als Skript erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="ca8da-136">Einige können Remote ausgeführt werden, andere müssen jedoch wie in der folgenden Tabelle angegeben lokal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="ca8da-137">Tools zum Wiederherstellen lync Server</span><span class="sxs-lookup"><span data-stu-id="ca8da-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca8da-138">Gewünschte Aktion</span><span class="sxs-lookup"><span data-stu-id="ca8da-138">To do this:</span></span></th>
<th><span data-ttu-id="ca8da-139">Zu verwendendes Tool oder Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ca8da-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-140">Neuen oder bereinigten Computer erstellen</span><span class="sxs-lookup"><span data-stu-id="ca8da-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca8da-141">Installationssoftware für das Windows-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="ca8da-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="ca8da-142">Installationssoftware für den SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca8da-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="ca8da-143">Snap-In "Certificates Microsoft Management Console“ (MMC), wenn Zertifikate mit einem exportierbaren privaten Schlüssel wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-144">Dateispeicherdaten wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="ca8da-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="ca8da-145">Standardtool zur Dateisystemverwaltung, z. B. Robocopy</span><span class="sxs-lookup"><span data-stu-id="ca8da-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-146">Leere Datenbanken wiederherstellen und Berechtigungen für Folgendes festlegen:</span><span class="sxs-lookup"><span data-stu-id="ca8da-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ca8da-147">zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="ca8da-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="ca8da-148">Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="ca8da-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="ca8da-149">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="ca8da-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="ca8da-150">Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="ca8da-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ca8da-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="ca8da-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-152">Wiederherstellen des Active Directory-Domänendienste Zeigers auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="ca8da-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ca8da-153">Wenn der Dienstverbindungspunkt vorübergehend nicht verfügbar ist, können Sie dieses Cmdlet erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="ca8da-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="ca8da-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ca8da-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-155">Importieren der Topologie-, Richtlinien-und Konfigurationseinstellungen in den zentralen Verwaltungsspeicher (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca8da-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-157">Veröffentlichen und Aktivieren der Topologie</span><span class="sxs-lookup"><span data-stu-id="ca8da-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="ca8da-158">Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="ca8da-158">Topology Builder</span></span></p>
<p><span data-ttu-id="ca8da-159">oder</span><span class="sxs-lookup"><span data-stu-id="ca8da-159">-or-</span></span></p>
<p><span data-ttu-id="ca8da-160">Publish-CsTopology und Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="ca8da-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-161">Zuletzt veröffentlichte Topologie aktivieren</span><span class="sxs-lookup"><span data-stu-id="ca8da-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="ca8da-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="ca8da-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-163">Neuinstallieren lync Server Komponenten</span><span class="sxs-lookup"><span data-stu-id="ca8da-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="ca8da-164">Lync Server-Setup</span><span class="sxs-lookup"><span data-stu-id="ca8da-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ca8da-165">Befindet sich im lync Server Installationsordner oder auf dem Datenträger unter \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="ca8da-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-166">Standort-Informationsdaten wiederherstellen (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca8da-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-168">Wiederherstellen persistenter Benutzerdaten ("rtcxds". mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="ca8da-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-170">Reaktionsgruppen-Konfigurationsdaten wiederherstellen (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca8da-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ca8da-172">Wenn die Konfiguration in einem neu bereitgestellten Pool ohne Reaktionsgruppen Daten in der Datenbank wiederhergestellt wird, sollten Sie die Option – OverwriteOwner verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="ca8da-173">Verwenden Sie diese Option, selbst wenn sich die wiederherzustellenden Daten in einem Pool mit dem gleichen vollqualifizierten Domänennamen (FQDN) befinden.</span><span class="sxs-lookup"><span data-stu-id="ca8da-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ca8da-174">Andernfalls wird der Import aufgrund der Kontaktobjekte zu den bereits in Active Directory vorhandenen Reaktionsgruppen nicht erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ca8da-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca8da-175">Folgende Datenbanken wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="ca8da-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="ca8da-176">Archivierungsdatenbank (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="ca8da-177">Überwachungsdatenbanken: Kommunikationsdatensatz-Datenbank (LcsCDR.mdf) und QoE-Datenbank (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ca8da-178">SQL-Serverdatenbank-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="ca8da-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca8da-179">Datenbank für beständigen Chat (MGS. mdf)</span><span class="sxs-lookup"><span data-stu-id="ca8da-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ca8da-180">SQL Server Wiederherstellungsverfahren oder Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="ca8da-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="ca8da-181">Sie können Import-CsPersistentChatData mit einer Datei verwenden, die von Export-CsPersistentChatData erstellt wurde, und die Daten werden in die Datenbank für beständigen Chat importiert.</span><span class="sxs-lookup"><span data-stu-id="ca8da-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="ca8da-182">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ca8da-182">Required Permissions</span></span>

<span data-ttu-id="ca8da-183">Benutzer müssen ein Mitglied der **RTCUniversalServerAdmins** -Gruppe sein, um alle in diesem Thema beschriebenen Befehle ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="ca8da-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="ca8da-184">Die meisten Sicherungs-und Wiederherstellungsbefehle unterstützen die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) nicht.</span><span class="sxs-lookup"><span data-stu-id="ca8da-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="ca8da-185">Zwei Ausnahmen sind die Cmdlets für beständigen Chat Export-CsPersistentChatData und Import-CsPersistentChatData, die von einem Benutzer ausgeführt werden müssen, der Mitglied der "cspersistentchatadministrator"-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="ca8da-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="ca8da-186">Zum Ausführen des lync Server-Bereitstellungs-Assistenten muss ein Benutzer auch Mitglied der lokalen Administratoren-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="ca8da-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

