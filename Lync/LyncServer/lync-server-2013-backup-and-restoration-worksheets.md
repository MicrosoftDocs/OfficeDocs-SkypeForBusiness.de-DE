---
title: 'Lync Server 2013: Arbeitsblätter zur Sicherung und Wiederherstellung'
description: 'Lync Server 2013: Arbeitsblätter zur Sicherung und Wiederherstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552317"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="db8dd-103">Arbeitsblätter zur Sicherung und Wiederherstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db8dd-103">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db8dd-104">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="db8dd-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="db8dd-105">Der Sicherungs-und Wiederherstellungsplan für Ihre Organisation sollte Details dazu enthalten, wie und wann Sie Daten und Einstellungen sichern.</span><span class="sxs-lookup"><span data-stu-id="db8dd-105">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="db8dd-106">Sie können die hier dargestellten Arbeitsblätter verwenden, um Sie bei der Dokumentation dieser Informationen für Ihre spezifische Bereitstellung und für die Sicherungs-und Wiederherstellungsanforderungen Ihrer Organisation zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-106">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="db8dd-107">Verwenden Sie die folgenden Arbeitsblätter, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Datenbankinformationen, Dateispeicher und Einstellungen für einen lync Server Pool oder Standard Edition-Server benötigen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-107">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="db8dd-108">Bewahren Sie eine oder mehrere Kopien dieser Arbeitsblätter an einem sicheren Ort auf, damit Sie leicht zugänglich sind, wenn Sie lync Server wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-108">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db8dd-109">In den Arbeitsblättern in diesem Abschnitt werden nur die Informationen behandelt, die erforderlich sind, um die Daten und Einstellungen von lync Server Datenbanken und Servern wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-109">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="db8dd-110">Wenn Sie andere Wiederherstellungsinformationen wie die Informationen zum Neuinstallieren von Betriebssystemen und anderer Software dokumentieren müssen, verwenden Sie die Bereitstellungspläne und Sicherungs-und Wiederherstellungspläne Ihrer Organisation, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-110">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="db8dd-111">Arbeitsblatt "Datenbanksicherung und-Wiederherstellung"</span><span class="sxs-lookup"><span data-stu-id="db8dd-111">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="db8dd-112">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen lync Server Datenbanken benötigen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-112">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="db8dd-113">Datenbankinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="db8dd-113">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db8dd-114">Database</span><span class="sxs-lookup"><span data-stu-id="db8dd-114">Database</span></span></th>
<th><span data-ttu-id="db8dd-115">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="db8dd-115">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="db8dd-116">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="db8dd-116">Backup schedule</span></span></th>
<th><span data-ttu-id="db8dd-117">Datenbanksicherungstool</span><span class="sxs-lookup"><span data-stu-id="db8dd-117">Database backup tool</span></span></th>
<th><span data-ttu-id="db8dd-118">Sicherungssätze</span><span class="sxs-lookup"><span data-stu-id="db8dd-118">Backup set</span></span></th>
<th><span data-ttu-id="db8dd-119">Sicherungsziel</span><span class="sxs-lookup"><span data-stu-id="db8dd-119">Backup destination</span></span></th>
<th><span data-ttu-id="db8dd-120">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="db8dd-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db8dd-121">RTC-Datenbank auf dem Back-End-Server für Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="db8dd-121">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="db8dd-122"><strong>Export-csuserdata "-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="db8dd-122"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="db8dd-123">Name</span><span class="sxs-lookup"><span data-stu-id="db8dd-123">Name:</span></span></p>
<p><span data-ttu-id="db8dd-124">Ablauf</span><span class="sxs-lookup"><span data-stu-id="db8dd-124">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db8dd-125">LcsLog-Datenbank (Standardname) auf Archivierungsdatenbank Server</span><span class="sxs-lookup"><span data-stu-id="db8dd-125">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db8dd-126">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="db8dd-126">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="db8dd-127">Name</span><span class="sxs-lookup"><span data-stu-id="db8dd-127">Name:</span></span></p>
<p><span data-ttu-id="db8dd-128">Ablauf</span><span class="sxs-lookup"><span data-stu-id="db8dd-128">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db8dd-129">LcsCdr-Datenbank auf Überwachungsdatenbank Server für Anruf Detaildatensätze (CDRs)</span><span class="sxs-lookup"><span data-stu-id="db8dd-129">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db8dd-130">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="db8dd-130">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="db8dd-131">Name</span><span class="sxs-lookup"><span data-stu-id="db8dd-131">Name:</span></span></p>
<p><span data-ttu-id="db8dd-132">Ablauf</span><span class="sxs-lookup"><span data-stu-id="db8dd-132">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db8dd-133">QoEMetrics-Datenbank auf Überwachungsdatenbank Server für QoE-Daten (Quality of Experience)</span><span class="sxs-lookup"><span data-stu-id="db8dd-133">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db8dd-134">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="db8dd-134">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="db8dd-135">Name</span><span class="sxs-lookup"><span data-stu-id="db8dd-135">Name:</span></span></p>
<p><span data-ttu-id="db8dd-136">Ablauf</span><span class="sxs-lookup"><span data-stu-id="db8dd-136">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db8dd-137">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="db8dd-137">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="db8dd-138">SQL Server-Verwaltungstool oder <strong>Export-CsPersistentChatData-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="db8dd-138">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="db8dd-139">Name</span><span class="sxs-lookup"><span data-stu-id="db8dd-139">Name:</span></span></p>
<p><span data-ttu-id="db8dd-140">Ablauf</span><span class="sxs-lookup"><span data-stu-id="db8dd-140">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db8dd-141">Für die folgenden Datenbanken ist keine Sicherung oder Wiederherstellung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="db8dd-141">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="db8dd-142">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="db8dd-142">Rtcdyn.</span></span> <span data-ttu-id="db8dd-143">Die flüchtigen Benutzerdaten in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="db8dd-143">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="db8dd-144">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="db8dd-144">Rtcab.</span></span> <span data-ttu-id="db8dd-145">Die Adressbuchdatenbank wird in Active Directory-Domänendienste automatisch aus der globalen Adressliste (GAL) neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="db8dd-145">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="db8dd-146">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="db8dd-146">Rgsdyn.</span></span> <span data-ttu-id="db8dd-147">Die Daten der transienten Reaktionsgruppen Dienste in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="db8dd-147">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="db8dd-148">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="db8dd-148">Cpsdyn.</span></span> <span data-ttu-id="db8dd-149">Die dynamischen Informationen für den Anwendung zum Parken von Anrufen sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="db8dd-149">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="db8dd-150">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="db8dd-150">MgcComp.</span></span> <span data-ttu-id="db8dd-151">Die Kompatibilitätsdatenbank für den beständigen Chat ist für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="db8dd-151">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="db8dd-152">Arbeitsblatt Dateispeicher Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="db8dd-152">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="db8dd-153">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen der Dateispeicher benötigen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-153">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="db8dd-154">Dateispeicher enthalten Daten wie Metadaten für Besprechungsinhalte, die Erfüllung von Kompatibilitäts Protokollen, Aktualisierungsprotokolle für Geräte Updates und Audiodateien für die Reaktionsgruppen-, Anruf Park-und Ankündigungs Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-154">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="db8dd-155">Dateispeicher Informationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="db8dd-155">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db8dd-156">Inhalt</span><span class="sxs-lookup"><span data-stu-id="db8dd-156">Content</span></span></th>
<th><span data-ttu-id="db8dd-157">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="db8dd-157">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="db8dd-158">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="db8dd-158">Backup schedule</span></span></th>
<th><span data-ttu-id="db8dd-159">Dateisystem-Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="db8dd-159">File system backup tool</span></span></th>
<th><span data-ttu-id="db8dd-160">Zu sichernde Dateifreigabe \*</span><span class="sxs-lookup"><span data-stu-id="db8dd-160">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="db8dd-161">Sicherungsziel</span><span class="sxs-lookup"><span data-stu-id="db8dd-161">Backup destination</span></span></th>
<th><span data-ttu-id="db8dd-162">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="db8dd-162">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db8dd-163">Lync Server Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="db8dd-163">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="db8dd-164">Standard Sicherungstool wie Robocopy</span><span class="sxs-lookup"><span data-stu-id="db8dd-164">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="db8dd-165">Auf dem Dateiserver für Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="db8dd-165">On file server for Enterprise Edition.</span></span> <span data-ttu-id="db8dd-166">Standard Edition für die Standard Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="db8dd-166">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="db8dd-167">Normalerweise eine pro Website.</span><span class="sxs-lookup"><span data-stu-id="db8dd-167">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="db8dd-168">Dateien mit dem Namen <strong>Meeting.Active</strong> sollten nicht gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="db8dd-168">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="db8dd-169">Diese Dateien werden verwendet und sind gesperrt, während eine Besprechung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="db8dd-169">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="db8dd-170">Arbeitsblatt "Einstellungen sichern und Wiederherstellen"</span><span class="sxs-lookup"><span data-stu-id="db8dd-170">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="db8dd-171">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Einstellungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="db8dd-171">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="db8dd-172">Einstellungsinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="db8dd-172">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db8dd-173">Database</span><span class="sxs-lookup"><span data-stu-id="db8dd-173">Database</span></span></th>
<th><span data-ttu-id="db8dd-174">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="db8dd-174">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="db8dd-175">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="db8dd-175">Backup schedule</span></span></th>
<th><span data-ttu-id="db8dd-176">Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="db8dd-176">Backup tool</span></span></th>
<th><span data-ttu-id="db8dd-177">Name der Konfigurationsdatei (XML)</span><span class="sxs-lookup"><span data-stu-id="db8dd-177">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="db8dd-178">Sicherungsspeicherort</span><span class="sxs-lookup"><span data-stu-id="db8dd-178">Backup location</span></span></th>
<th><span data-ttu-id="db8dd-179">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="db8dd-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db8dd-180">XDS-Datenbank im zentralen Verwaltungsspeicher für die Topologie-Konfiguration (Global)</span><span class="sxs-lookup"><span data-stu-id="db8dd-180">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="db8dd-181"><strong>Export-CsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="db8dd-181"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db8dd-182">LIS-Datenbank im zentralen Verwaltungsspeicher für E9-1-1-Standortinformationen (Global)</span><span class="sxs-lookup"><span data-stu-id="db8dd-182">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db8dd-183"><strong>Export-CsLisConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="db8dd-183"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db8dd-184">RgsConfig-Datenbank auf dem Back-End-Server für die Konfiguration von Reaktionsgruppen (Pool)</span><span class="sxs-lookup"><span data-stu-id="db8dd-184">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db8dd-185"><strong>Export-CsRgsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="db8dd-185"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

