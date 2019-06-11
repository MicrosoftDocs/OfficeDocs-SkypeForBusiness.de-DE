---
title: 'Lync Server 2013: Arbeitsblätter zum Sichern und Wiederherstellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca10b848dfa1f6cf53724b364cf53b1fc0fad90
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="257ef-102">Arbeitsblätter zum Sichern und Wiederherstellen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="257ef-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="257ef-103">_**Letztes Änderungsdatum des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="257ef-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="257ef-104">Der Sicherungs-und Wiederherstellungsplan für Ihre Organisation sollte Details dazu enthalten, wie und wann Sie Daten und Einstellungen sichern.</span><span class="sxs-lookup"><span data-stu-id="257ef-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="257ef-105">Sie können die hier vorgestellten Arbeitsblätter dazu verwenden, diese Informationen für Ihre spezifische Bereitstellung und für die Sicherungs-und Wiederherstellungsanforderungen Ihrer Organisation zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="257ef-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="257ef-106">Verwenden Sie die folgenden Arbeitsblätter zum Aufzeichnen der Informationen, die Sie zum Sichern und Wiederherstellen von Datenbank-, Dateispeicher-und Einstellungsinformationen für einen lync Server-Pool oder Standard Edition-Server benötigen.</span><span class="sxs-lookup"><span data-stu-id="257ef-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="257ef-107">Bewahren Sie eine oder mehrere Kopien dieser Arbeitsblätter an einem sicheren Ort auf, damit Sie leicht zugänglich sind, wenn Sie lync Server wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="257ef-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="257ef-108">Die Arbeitsblätter in diesem Abschnitt beziehen sich nur auf die Informationen, die erforderlich sind, um die Daten und Einstellungen der lync Server-Datenbanken und-Server wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="257ef-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="257ef-109">Wenn Sie andere Wiederherstellungsinformationen wie die Informationen zum erneuten Installieren von Betriebssystemen und anderer Software dokumentieren müssen, verwenden Sie die Bereitstellungspläne und Sicherungs-und Wiederherstellungspläne Ihrer Organisation, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="257ef-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="257ef-110">Arbeitsblatt für Datenbanksicherung und-Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="257ef-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="257ef-111">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von lync Server-Datenbanken benötigen.</span><span class="sxs-lookup"><span data-stu-id="257ef-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="257ef-112">Datenbankinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="257ef-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="257ef-113">Datenbank</span><span class="sxs-lookup"><span data-stu-id="257ef-113">Database</span></span></th>
<th><span data-ttu-id="257ef-114">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="257ef-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="257ef-115">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="257ef-115">Backup schedule</span></span></th>
<th><span data-ttu-id="257ef-116">Datenbanksicherungstool</span><span class="sxs-lookup"><span data-stu-id="257ef-116">Database backup tool</span></span></th>
<th><span data-ttu-id="257ef-117">Sicherungssatz</span><span class="sxs-lookup"><span data-stu-id="257ef-117">Backup set</span></span></th>
<th><span data-ttu-id="257ef-118">Backup-Ziel</span><span class="sxs-lookup"><span data-stu-id="257ef-118">Backup destination</span></span></th>
<th><span data-ttu-id="257ef-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="257ef-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="257ef-120">RTC-Datenbank auf dem Back-End-Server für Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="257ef-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="257ef-121"><strong>Export-CsUserData-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="257ef-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="257ef-122">Namen</span><span class="sxs-lookup"><span data-stu-id="257ef-122">Name:</span></span></p>
<p><span data-ttu-id="257ef-123">Ablauf</span><span class="sxs-lookup"><span data-stu-id="257ef-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="257ef-124">LcsLog (Standardname)-Datenbank auf dem Archivierungsdaten Bankserver</span><span class="sxs-lookup"><span data-stu-id="257ef-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="257ef-125">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="257ef-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="257ef-126">Namen</span><span class="sxs-lookup"><span data-stu-id="257ef-126">Name:</span></span></p>
<p><span data-ttu-id="257ef-127">Ablauf</span><span class="sxs-lookup"><span data-stu-id="257ef-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="257ef-128">LcsCdr-Datenbank zum Überwachen des Datenbankservers für Anruf Detaildatensätze (CDRs)</span><span class="sxs-lookup"><span data-stu-id="257ef-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="257ef-129">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="257ef-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="257ef-130">Namen</span><span class="sxs-lookup"><span data-stu-id="257ef-130">Name:</span></span></p>
<p><span data-ttu-id="257ef-131">Ablauf</span><span class="sxs-lookup"><span data-stu-id="257ef-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="257ef-132">Datenbank QoEMetrics werden-Datenbank zum Überwachen des Datenbankservers für QoE-Daten (Quality of Experience)</span><span class="sxs-lookup"><span data-stu-id="257ef-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="257ef-133">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="257ef-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="257ef-134">Namen</span><span class="sxs-lookup"><span data-stu-id="257ef-134">Name:</span></span></p>
<p><span data-ttu-id="257ef-135">Ablauf</span><span class="sxs-lookup"><span data-stu-id="257ef-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="257ef-136">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="257ef-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="257ef-137">SQL Server-Verwaltungstool oder <strong>Export-CsPersistentChatData-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="257ef-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="257ef-138">Namen</span><span class="sxs-lookup"><span data-stu-id="257ef-138">Name:</span></span></p>
<p><span data-ttu-id="257ef-139">Ablauf</span><span class="sxs-lookup"><span data-stu-id="257ef-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="257ef-140">Für die folgenden Datenbanken ist keine Sicherung oder Wiederherstellung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="257ef-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="257ef-141">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="257ef-141">Rtcdyn.</span></span> <span data-ttu-id="257ef-142">Die flüchtigen Benutzerdaten in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="257ef-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="257ef-143">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="257ef-143">Rtcab.</span></span> <span data-ttu-id="257ef-144">Die Adressbuchdatenbank wird automatisch aus der globalen Adressliste (Global Address List, GAL) in den Active Directory-Domänendiensten neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="257ef-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="257ef-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="257ef-145">Rgsdyn.</span></span> <span data-ttu-id="257ef-146">Die Daten in dieser Datenbank für transiente Reaktionsgruppen Dienste sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="257ef-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="257ef-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="257ef-147">Cpsdyn.</span></span> <span data-ttu-id="257ef-148">Die dynamischen Informationen für die Anwendung für den Parken von Anrufen sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="257ef-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="257ef-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="257ef-149">MgcComp.</span></span> <span data-ttu-id="257ef-150">Die Kompatibilitätsdatenbank für beständigen Chat ist für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="257ef-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="257ef-151">Arbeitsblatt zum Sichern und Wiederherstellen von Datei speichern</span><span class="sxs-lookup"><span data-stu-id="257ef-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="257ef-152">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen der Dateispeicher benötigen.</span><span class="sxs-lookup"><span data-stu-id="257ef-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="257ef-153">Dateispeicher enthalten Daten wie Metadaten für Besprechungsinhalte, Besprechung von Kompatibilitäts Protokollen, Aktualisierungsprotokolle für Geräte Updates und Audiodateien für die Reaktionsgruppe, den Anruf Park und Ankündigungs Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="257ef-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="257ef-154">Dateispeicher Informationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="257ef-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="257ef-155">Inhalt</span><span class="sxs-lookup"><span data-stu-id="257ef-155">Content</span></span></th>
<th><span data-ttu-id="257ef-156">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="257ef-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="257ef-157">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="257ef-157">Backup schedule</span></span></th>
<th><span data-ttu-id="257ef-158">Dateisystem-Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="257ef-158">File system backup tool</span></span></th>
<th><span data-ttu-id="257ef-159">Zu sichernde Dateifreigabe \*</span><span class="sxs-lookup"><span data-stu-id="257ef-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="257ef-160">Backup-Ziel</span><span class="sxs-lookup"><span data-stu-id="257ef-160">Backup destination</span></span></th>
<th><span data-ttu-id="257ef-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="257ef-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="257ef-162">Lync Server-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="257ef-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="257ef-163">Standard Sicherungstool wie Robocopy</span><span class="sxs-lookup"><span data-stu-id="257ef-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="257ef-164">Auf Dateiserver für Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="257ef-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="257ef-165">Standardmäßig für die Standard Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="257ef-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="257ef-166">In der Regel eine pro Website.</span><span class="sxs-lookup"><span data-stu-id="257ef-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="257ef-167">Dateien mit dem Namen " <strong>Meeting. Active</strong> " sollten nicht gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="257ef-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="257ef-168">Diese Dateien werden verwendet und sind gesperrt, während eine Besprechung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="257ef-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="257ef-169">Arbeitsblatt ' Sicherungs-und Wiederherstellungseinstellungen '</span><span class="sxs-lookup"><span data-stu-id="257ef-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="257ef-170">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Einstellungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="257ef-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="257ef-171">Einstellungsinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="257ef-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="257ef-172">Datenbank</span><span class="sxs-lookup"><span data-stu-id="257ef-172">Database</span></span></th>
<th><span data-ttu-id="257ef-173">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="257ef-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="257ef-174">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="257ef-174">Backup schedule</span></span></th>
<th><span data-ttu-id="257ef-175">Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="257ef-175">Backup tool</span></span></th>
<th><span data-ttu-id="257ef-176">Konfigurationsdatei-Name (XML)</span><span class="sxs-lookup"><span data-stu-id="257ef-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="257ef-177">Sicherungsspeicherort</span><span class="sxs-lookup"><span data-stu-id="257ef-177">Backup location</span></span></th>
<th><span data-ttu-id="257ef-178">Hinweise</span><span class="sxs-lookup"><span data-stu-id="257ef-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="257ef-179">XDS-Datenbank im zentralen Verwaltungsspeicher für Topologie-Konfiguration (Global)</span><span class="sxs-lookup"><span data-stu-id="257ef-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="257ef-180"><strong>Export-CsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="257ef-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="257ef-181">LIS-Datenbank im zentralen Verwaltungsspeicher für E9-1-1-Standortinformationen (Global)</span><span class="sxs-lookup"><span data-stu-id="257ef-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="257ef-182"><strong>Export-CsLisConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="257ef-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="257ef-183">RgsConfig-Datenbank auf dem Back-End-Server für die Konfiguration der Reaktionsgruppe (Pool)</span><span class="sxs-lookup"><span data-stu-id="257ef-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="257ef-184"><strong>Export-CsRgsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="257ef-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

