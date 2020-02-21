---
title: 'Lync Server 2013: Arbeitsblätter zur Sicherung und Wiederherstellung'
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
ms.openlocfilehash: 3fcf163893a84e4b9244e43b12c702cf0076b1ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="d6fb1-102">Arbeitsblätter zur Sicherung und Wiederherstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6fb1-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6fb1-103">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="d6fb1-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="d6fb1-104">Der Sicherungs-und Wiederherstellungsplan für Ihre Organisation sollte Details dazu enthalten, wie und wann Sie Daten und Einstellungen sichern.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="d6fb1-105">Sie können die hier dargestellten Arbeitsblätter verwenden, um Sie bei der Dokumentation dieser Informationen für Ihre spezifische Bereitstellung und für die Sicherungs-und Wiederherstellungsanforderungen Ihrer Organisation zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="d6fb1-106">Verwenden Sie die folgenden Arbeitsblätter, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Datenbankinformationen, Dateispeicher und Einstellungen für einen lync Server Pool oder Standard Edition-Server benötigen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="d6fb1-107">Bewahren Sie eine oder mehrere Kopien dieser Arbeitsblätter an einem sicheren Ort auf, damit Sie leicht zugänglich sind, wenn Sie lync Server wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6fb1-108">In den Arbeitsblättern in diesem Abschnitt werden nur die Informationen behandelt, die erforderlich sind, um die Daten und Einstellungen von lync Server Datenbanken und Servern wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="d6fb1-109">Wenn Sie andere Wiederherstellungsinformationen wie die Informationen zum Neuinstallieren von Betriebssystemen und anderer Software dokumentieren müssen, verwenden Sie die Bereitstellungspläne und Sicherungs-und Wiederherstellungspläne Ihrer Organisation, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="d6fb1-110">Arbeitsblatt "Datenbanksicherung und-Wiederherstellung"</span><span class="sxs-lookup"><span data-stu-id="d6fb1-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="d6fb1-111">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen lync Server Datenbanken benötigen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="d6fb1-112">Datenbankinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d6fb1-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="d6fb1-113">Datenbank</span><span class="sxs-lookup"><span data-stu-id="d6fb1-113">Database</span></span></th>
<th><span data-ttu-id="d6fb1-114">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="d6fb1-115">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="d6fb1-115">Backup schedule</span></span></th>
<th><span data-ttu-id="d6fb1-116">Datenbanksicherungstool</span><span class="sxs-lookup"><span data-stu-id="d6fb1-116">Database backup tool</span></span></th>
<th><span data-ttu-id="d6fb1-117">Sicherungssätze</span><span class="sxs-lookup"><span data-stu-id="d6fb1-117">Backup set</span></span></th>
<th><span data-ttu-id="d6fb1-118">Sicherungsziel</span><span class="sxs-lookup"><span data-stu-id="d6fb1-118">Backup destination</span></span></th>
<th><span data-ttu-id="d6fb1-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6fb1-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6fb1-120">RTC-Datenbank auf dem Back-End-Server für Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="d6fb1-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="d6fb1-121"><strong>Export-csuserdata "-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6fb1-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="d6fb1-122">Name</span><span class="sxs-lookup"><span data-stu-id="d6fb1-122">Name:</span></span></p>
<p><span data-ttu-id="d6fb1-123">Ablauf</span><span class="sxs-lookup"><span data-stu-id="d6fb1-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6fb1-124">LcsLog-Datenbank (Standardname) auf Archivierungsdatenbank Server</span><span class="sxs-lookup"><span data-stu-id="d6fb1-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6fb1-125">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="d6fb1-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="d6fb1-126">Name</span><span class="sxs-lookup"><span data-stu-id="d6fb1-126">Name:</span></span></p>
<p><span data-ttu-id="d6fb1-127">Ablauf</span><span class="sxs-lookup"><span data-stu-id="d6fb1-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6fb1-128">LcsCdr-Datenbank auf Überwachungsdatenbank Server für Anruf Detaildatensätze (CDRs)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6fb1-129">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="d6fb1-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="d6fb1-130">Name</span><span class="sxs-lookup"><span data-stu-id="d6fb1-130">Name:</span></span></p>
<p><span data-ttu-id="d6fb1-131">Ablauf</span><span class="sxs-lookup"><span data-stu-id="d6fb1-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6fb1-132">QoEMetrics-Datenbank auf Überwachungsdatenbank Server für QoE-Daten (Quality of Experience)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6fb1-133">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="d6fb1-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="d6fb1-134">Name</span><span class="sxs-lookup"><span data-stu-id="d6fb1-134">Name:</span></span></p>
<p><span data-ttu-id="d6fb1-135">Ablauf</span><span class="sxs-lookup"><span data-stu-id="d6fb1-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6fb1-136">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="d6fb1-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="d6fb1-137">SQL Server-Verwaltungstool oder <strong>Export-CsPersistentChatData-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6fb1-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="d6fb1-138">Name</span><span class="sxs-lookup"><span data-stu-id="d6fb1-138">Name:</span></span></p>
<p><span data-ttu-id="d6fb1-139">Ablauf</span><span class="sxs-lookup"><span data-stu-id="d6fb1-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6fb1-140">Für die folgenden Datenbanken ist keine Sicherung oder Wiederherstellung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d6fb1-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="d6fb1-141">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-141">Rtcdyn.</span></span> <span data-ttu-id="d6fb1-142">Die flüchtigen Benutzerdaten in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="d6fb1-143">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-143">Rtcab.</span></span> <span data-ttu-id="d6fb1-144">Die Adressbuchdatenbank wird in Active Directory-Domänendienste automatisch aus der globalen Adressliste (GAL) neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="d6fb1-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-145">Rgsdyn.</span></span> <span data-ttu-id="d6fb1-146">Die Daten der transienten Reaktionsgruppen Dienste in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="d6fb1-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-147">Cpsdyn.</span></span> <span data-ttu-id="d6fb1-148">Die dynamischen Informationen für den Anwendung zum Parken von Anrufen sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="d6fb1-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-149">MgcComp.</span></span> <span data-ttu-id="d6fb1-150">Die Kompatibilitätsdatenbank für den beständigen Chat ist für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="d6fb1-151">Arbeitsblatt Dateispeicher Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d6fb1-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="d6fb1-152">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen der Dateispeicher benötigen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="d6fb1-153">Dateispeicher enthalten Daten wie Metadaten für Besprechungsinhalte, die Erfüllung von Kompatibilitäts Protokollen, Aktualisierungsprotokolle für Geräte Updates und Audiodateien für die Reaktionsgruppen-, Anruf Park-und Ankündigungs Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="d6fb1-154">Dateispeicher Informationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d6fb1-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="d6fb1-155">Inhalt</span><span class="sxs-lookup"><span data-stu-id="d6fb1-155">Content</span></span></th>
<th><span data-ttu-id="d6fb1-156">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="d6fb1-157">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="d6fb1-157">Backup schedule</span></span></th>
<th><span data-ttu-id="d6fb1-158">Dateisystem-Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="d6fb1-158">File system backup tool</span></span></th>
<th><span data-ttu-id="d6fb1-159">Zu sichernde Dateifreigabe \*</span><span class="sxs-lookup"><span data-stu-id="d6fb1-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="d6fb1-160">Sicherungsziel</span><span class="sxs-lookup"><span data-stu-id="d6fb1-160">Backup destination</span></span></th>
<th><span data-ttu-id="d6fb1-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6fb1-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6fb1-162">Lync Server Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="d6fb1-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="d6fb1-163">Standard Sicherungstool wie Robocopy</span><span class="sxs-lookup"><span data-stu-id="d6fb1-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="d6fb1-164">Auf dem Dateiserver für Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="d6fb1-165">Standard Edition für die Standard Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="d6fb1-166">Normalerweise eine pro Website.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d6fb1-167">Dateien mit dem Namen <strong>Meeting.Active</strong> sollten nicht gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="d6fb1-168">Diese Dateien werden verwendet und sind gesperrt, während eine Besprechung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="d6fb1-169">Arbeitsblatt "Einstellungen sichern und Wiederherstellen"</span><span class="sxs-lookup"><span data-stu-id="d6fb1-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="d6fb1-170">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Einstellungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="d6fb1-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="d6fb1-171">Einstellungsinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d6fb1-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="d6fb1-172">Datenbank</span><span class="sxs-lookup"><span data-stu-id="d6fb1-172">Database</span></span></th>
<th><span data-ttu-id="d6fb1-173">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="d6fb1-174">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="d6fb1-174">Backup schedule</span></span></th>
<th><span data-ttu-id="d6fb1-175">Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="d6fb1-175">Backup tool</span></span></th>
<th><span data-ttu-id="d6fb1-176">Name der Konfigurationsdatei (XML)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="d6fb1-177">Sicherungsspeicherort</span><span class="sxs-lookup"><span data-stu-id="d6fb1-177">Backup location</span></span></th>
<th><span data-ttu-id="d6fb1-178">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6fb1-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6fb1-179">XDS-Datenbank im zentralen Verwaltungsspeicher für die Topologie-Konfiguration (Global)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="d6fb1-180"><strong>Export-CsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6fb1-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6fb1-181">LIS-Datenbank im zentralen Verwaltungsspeicher für E9-1-1-Standortinformationen (Global)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6fb1-182"><strong>Export-CsLisConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6fb1-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6fb1-183">RgsConfig-Datenbank auf dem Back-End-Server für die Konfiguration von Reaktionsgruppen (Pool)</span><span class="sxs-lookup"><span data-stu-id="d6fb1-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6fb1-184"><strong>Export-CsRgsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6fb1-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

