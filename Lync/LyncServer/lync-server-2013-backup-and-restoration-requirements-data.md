---
title: 'Lync Server 2013: Anforderungen an die Sicherung und Wiederherstellung: Daten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca6823c1f3e8265f7b06ea0d175b58d42ef4a08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="6a5d9-102">Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data</span><span class="sxs-lookup"><span data-stu-id="6a5d9-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a5d9-103">_**Letztes Änderungsstand des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="6a5d9-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="6a5d9-104">Lync Server verwendet Einstellungen und Konfigurationsinformationen, die in Datenbanken gespeichert sind, sowie Daten, die in Datenbanken und Datei speichern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="6a5d9-105">In diesem Thema werden die Daten beschrieben, die Sie sichern müssen, damit der Dienst wiederhergestellt werden kann, wenn in Ihrer Organisation ein Fehler oder Ausfall auftritt, sowie die von lync Server verwendeten Daten und Komponenten identifiziert werden, die separat gesichert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="6a5d9-106">Einstellungen und Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6a5d9-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="6a5d9-107">Dieses Thema enthält Verfahren zum Sichern und Wiederherstellen der Einstellungen und Konfigurationsinformationen, die für die Wiederherstellung des lync Server Diensts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="6a5d9-108">Die Konfigurationsinformationen befinden sich im zentralen Verwaltungsspeicher oder in einer anderen Back-End-Datenbank oder auf Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="6a5d9-109">In der folgenden Tabelle sind die Einstellungen und Konfigurationsinformationen aufgeführt, die Sie sichern und wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="6a5d9-110">Einstellungen und Konfigurationsdaten</span><span class="sxs-lookup"><span data-stu-id="6a5d9-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a5d9-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6a5d9-111">Type of data</span></span></th>
<th><span data-ttu-id="6a5d9-112">Speicherort</span><span class="sxs-lookup"><span data-stu-id="6a5d9-112">Where stored</span></span></th>
<th><span data-ttu-id="6a5d9-113">Beschreibung/Sicherungszeitpunkt</span><span class="sxs-lookup"><span data-stu-id="6a5d9-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a5d9-114">Topologiekonfigurationsinformationen</span><span class="sxs-lookup"><span data-stu-id="6a5d9-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-115">Zentraler Verwaltungsspeicher (Datenbank: XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-116">Topologie, Richtlinie und Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="6a5d9-117">Sichern Sie sich mit ihren regulären Sicherungen und nachdem Sie lync Server-Systemsteuerung oder Cmdlets zum Ändern Ihrer Konfiguration oder Richtlinien verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a5d9-118">Standortinformationen</span><span class="sxs-lookup"><span data-stu-id="6a5d9-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-119">Zentraler Verwaltungsspeicher (Datenbank: Lis. mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-p103">Enterprise-VoIP-Konfigurationsinformationen für 9-1-1 (erweitert) (E9-1-1). Diese Informationen sind im Allgemeinen statisch.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-p103">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information. This information is generally static.</span></span></p>
<p><span data-ttu-id="6a5d9-122">Sicherung im Rahmen der regulären Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a5d9-123">Informationen zur Reaktionsgruppenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="6a5d9-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-124">Back-End-Server oder Standard Edition-Server (Datenbank: RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-125">Gruppen, Warteschlangen und Workflows für Reaktionsgruppen-Agents.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="6a5d9-126">Sicherung im Rahmen der regulären Sicherungen und nach dem Hinzufügen oder Ändern von Agentgruppen, Warteschlangen oder Workflows.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="6a5d9-127">Datenanforderungen</span><span class="sxs-lookup"><span data-stu-id="6a5d9-127">Data Requirements</span></span>

<span data-ttu-id="6a5d9-128">Im folgenden finden Sie eine Liste der lync Server Daten, die Sie sichern müssen, damit Sie lync Server Dienst im Falle eines Fehlers wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="6a5d9-129">Beachten Sie, dass einige Datentypen für die Wiederherstellung nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="6a5d9-130">Dieses Thema enthält keine Verfahren zum Sichern dieser Datentypen, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="6a5d9-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="6a5d9-131">Temporäre Benutzerdaten, wie z. B. Endgeräte und Abonnements, aktive Konferenzserver und vorübergehende Konferenzstatus (Datenbank: RtcDyn.mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="6a5d9-132">Adressbuchdaten (Datenbanken: RTCAb. mdf und Rtcab1. mdf).</span><span class="sxs-lookup"><span data-stu-id="6a5d9-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="6a5d9-133">Die Adressbuchdatenbank wird automatisch aus Active Directory-Domänendienste neu generiert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="6a5d9-134">Dynamische Informationen für den Anwendung zum Parken von Anrufen (Datenbank: CpsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="6a5d9-135">Transiente Reaktionsgruppen Daten wie Agent-Anmeldestatus und warte Informationen für Anrufe (Datenbank: RgsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="6a5d9-136">Die Kompatibilitätsdatenbank für den beständigen Chat (Datenbank: MgcComp. mdf).</span><span class="sxs-lookup"><span data-stu-id="6a5d9-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="6a5d9-137">Wenn Sie die Compliance für beständigen Chat aktiviert haben, sind die Informationen in der Kompatibilitätsdatenbank für beständigen Chat vorübergehend, solange Sie einen Adapter konfiguriert haben, um Informationen aus der Datenbank zu lesen und in ein alternatives Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="6a5d9-138">Die Kompatibilitätsdatenbank für den beständigen Chat wird daher als vorübergehend betrachtet.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="6a5d9-139">Beständiger Chat von lync Server 2013 Server wird mit einem XML-Adapter ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="6a5d9-140">Sie können auch benutzerdefinierte Adapter installieren, die diese Daten entgegennehmen und in andere Quellen wie Exchange Hosted Archives migrieren.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="6a5d9-141">In der folgenden Tabelle sind die Daten aufgeführt, die Sie sichern und wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="6a5d9-142">In Datenbanken gespeicherte Daten</span><span class="sxs-lookup"><span data-stu-id="6a5d9-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a5d9-143">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6a5d9-143">Type of data</span></span></th>
<th><span data-ttu-id="6a5d9-144">Speicherort</span><span class="sxs-lookup"><span data-stu-id="6a5d9-144">Where stored</span></span></th>
<th><span data-ttu-id="6a5d9-145">Beschreibung/Sicherungszeitpunkt</span><span class="sxs-lookup"><span data-stu-id="6a5d9-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a5d9-146">Dauerhafte Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="6a5d9-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-147">Back-End-Server oder Standard Edition-Server (Datenbank: "rtcxds". mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-148">Benutzerrechte, Benutzerkontaktlisten, Server- oder Pooldaten, geplante Konferenzen usw.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="6a5d9-149">In eine Konferenz hochgeladene Inhalte sind in diesen Benutzerdaten nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="6a5d9-150">Sicherung im Rahmen der regulären Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-150">Back up with your regular backups.</span></span> <span data-ttu-id="6a5d9-151">Diese Informationen sind dynamisch, aber der Verlust von Updates ist für lync Server nicht katastrophal, wenn Sie die letzte reguläre Sicherung wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="6a5d9-152">Sie können diese Daten häufiger sichern, wenn Kontaktlisten für Ihre Organisation eine wichtige Rolle spielen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a5d9-153">Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="6a5d9-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-154">Archivierungsdatenbank (Datenbank: LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="6a5d9-155">Diese Daten können auf Exchange 2013 gespeichert werden, wenn Sie die Option Microsoft Exchange Integration aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="6a5d9-156">Andernfalls werden diese Daten in einer lync Server Archivierungsdatenbank aufbewahrt, die möglicherweise mit einer anderen lync Server Datenbank oder eigenständig auf einem separaten Daten Bank Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-157">Instant Messaging (IM)- und Besprechungsinhalte.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="6a5d9-158">Diese Daten sind für lync Server nicht wichtig, aber Sie können für Ihre Organisation für regulatorische Zwecke von entscheidender Bedeutung sein.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="6a5d9-159">Legen Sie Ihren Sicherungszeitplan entsprechend fest.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a5d9-160">Überwachungsdaten</span><span class="sxs-lookup"><span data-stu-id="6a5d9-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-161">Überwachungsdatenbanken (LcsCDR.mdf und QoeMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="6a5d9-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="6a5d9-162">Diese Datenbankenkönnen mit einer anderen lync Server Datenbank oder eigenständig auf einem separaten Daten Bank Server zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-163">Kommunikationsdatensätze (LcsCDR. mdf) und QoE-Metrik (Quality of Experience) (QoeMetrics. mdf).</span><span class="sxs-lookup"><span data-stu-id="6a5d9-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="6a5d9-p112">Kommunikationsdatensätze sind dynamisch und können für Ihr Unternehmen eine wichtige Rolle spielen. Berücksichtigen Sie bei der Festlegung Ihres Sicherungszeitplans, ob Sie diese Datensätze zur Einhaltung von Bestimmungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-p112">Call detail records are dynamic and may be critical to your business. Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="6a5d9-166">QoE-Informationen sind dynamisch.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="6a5d9-167">Der Verlust von QoE-Daten ist für den Betrieb von lync Server nicht entscheidend, kann jedoch für Ihr Unternehmen von entscheidender Bedeutung sein.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="6a5d9-168">Berücksichtigen Sie bei der Festlegung Ihres Sicherungszeitplans, wie wichtig diese Informationen für Ihre Organisation sind.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a5d9-169">Daten für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6a5d9-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-170">Datenbank für beständigen Chat (MGD. mdf).</span><span class="sxs-lookup"><span data-stu-id="6a5d9-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="6a5d9-171">Diese Datenbank kann mit einer anderen lync Server Datenbank oder eigenständig auf einem separaten Daten Bank Server zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-172">Daten für beständigen Chat sind tatsächliche Chatinhalte, die in Chatrooms veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="6a5d9-173">Diese Daten sind oft geschäftskritisch.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="6a5d9-174">Sie können SQL Server Sicherung verwenden oder die Datenbank mithilfe des Cmdlets <strong>Export-CsPersistentChatData</strong> exportieren, das in lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="6a5d9-175">Für die Wiederherstellung der Daten können Sie die Datenbank bis zum Ende der letzten vollständigen Sicherung importieren und wiederherstellen, was bedeutet, dass Sie die Datenbank nicht bis zum Fehler zurücksetzen können.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="6a5d9-176">Dateispeicher-Datenanforderungen</span><span class="sxs-lookup"><span data-stu-id="6a5d9-176">File Store Data Requirements</span></span>

<span data-ttu-id="6a5d9-177">In einer Enterprise Edition-Bereitstellung befindet sich der lync Server Dateispeicher in der Regel auf einem Datei Server.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="6a5d9-178">In einer Standard Edition-Bereitstellung befindet sich der lync Server Dateispeicher standardmäßig auf dem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="6a5d9-179">In der Regel gibt es einen lync Server Dateispeicher, der für eine Website freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="6a5d9-180">Der Dateispeicher für beständigen Chat verwendet dieselbe Dateifreigabe wie der lync Server Dateispeichers.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="6a5d9-181">Speicherorte für Dateispeicher werden \\ \\als\\Serverfreigabe Name identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="6a5d9-182">Um die spezifischen Speicherorte ihrer Dateispeicher zu finden, öffnen Sie den Topologie-Generator und schauen Sie sich den Knoten **Dateispeicher** an.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="6a5d9-183">In der folgenden Tabelle werden die Dateispeicher beschrieben, die Sie sichern und wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="6a5d9-184">Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="6a5d9-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a5d9-185">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6a5d9-185">Type of data</span></span></th>
<th><span data-ttu-id="6a5d9-186">Speicherort</span><span class="sxs-lookup"><span data-stu-id="6a5d9-186">Where stored</span></span></th>
<th><span data-ttu-id="6a5d9-187">Beschreibung/Sicherungszeitpunkt</span><span class="sxs-lookup"><span data-stu-id="6a5d9-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a5d9-188">Lync Server-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="6a5d9-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-189">Normalerweise auf einem Dateiserver, einem Dateicluster oder einem Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="6a5d9-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="6a5d9-190">Besprechungsinhalte, Metadaten für Besprechungsinhalte, Kompatibilitäts Protokolle für Anwendungsdateien, Updatedateien für Geräte Updates, Audiodateien für Reaktionsgruppen, Parken von Anrufen und Ankündigungs Anwendungen sowie Dateien, die in beständigen Chatrooms bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="6a5d9-191">Sicherung im Rahmen der regulären Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="6a5d9-192">Zusätzliche Sicherungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6a5d9-192">Additional Backup Requirements</span></span>

<span data-ttu-id="6a5d9-193">Um sicherzustellen, dass lync Server Dienste im Falle eines Fehlers wiederhergestellt werden können, müssen Sie einige erforderliche Komponenten sichern, die nicht Teil von lync Server selbst sind.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="6a5d9-194">Die folgenden Komponenten werden im Rahmen des in diesem Dokument beschriebenen lync Server Sicherungs-und Wiederherstellungsprozesses nicht gesichert oder wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="6a5d9-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="6a5d9-195">**Active Directory-Domänendienste**   Sie AD DS mit Active Directory Tools sichern müssen, gleichzeitig sichern Sie lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="6a5d9-196">Es ist wichtig, dass AD DS mit lync Server synchronisiert bleibt, um Probleme zu vermeiden, die auftreten können, wenn lync Server Kontaktobjekte erwartet, die nicht mit denen in AD DS übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="6a5d9-197">In AD DS werden die folgenden Einstellungen gespeichert, die von lync Server verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6a5d9-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="6a5d9-198">SIP-URI des Benutzers und andere Benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="6a5d9-199">Kontaktobjekte für Anwendungen wie Reaktionsgruppen und Konferenzzentrale.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="6a5d9-200">Ein Zeiger auf das zentraler Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="6a5d9-201">Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt) und lync Server Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="6a5d9-202">Ausführliche Informationen zum Sichern und Wiederherstellen AD DS in Windows Server 2008 finden Sie unter "AD DS Schritt-für-Schritt-Anleitung zur Sicherung und wieder [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105)Herstellung" unter.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="6a5d9-203">**Zertifizierungsstellen und Zertifikate**   verwenden die Richtlinie Ihrer Organisation für die Sicherung Ihrer Zertifizierungsstelle (Certification Authority, ca) und Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="6a5d9-204">Wenn Sie exportierbare private Schlüssel verwenden, können Sie das Zertifikat und den privaten Schlüssel sichern und dann exportieren, wenn Sie die Verfahren in diesem Dokument verwenden, um lync Server wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="6a5d9-205">Wenn Sie eine interne Zertifizierungsstelle verwenden, können Sie sich erneut anmelden, wenn Sie lync Server wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="6a5d9-206">Sie müssen den privaten Schlüssel unbedingt an einem sicheren Ort verwahren, damit er beim Ausfall eines Computers verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="6a5d9-207">**System Center Operations Manager**   Wenn Sie Microsoft System Center Operations Manager (ehemals Microsoft Operations Manager) zum Überwachen Ihrer lync Server-Bereitstellung verwenden, können Sie die Daten, die beim Überwachen von lync Server erstellt werden, optional sichern.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="6a5d9-208">Verwenden Sie den standardmäßigen SQL Server Sicherungsprozess zum Sichern von System Center Operations Manager-Dateien.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="6a5d9-209">Diese Dateien werden nicht in die Wiederherstellung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="6a5d9-210">**PSTN-Gateway-Konfiguration (Public Switched Telephone Network)**   Wenn Sie Enterprise-VoIP-oder Survivable Branch-Appliances verwenden, müssen Sie die Konfiguration des PSTN-Gateways sichern.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="6a5d9-211">Informationen zum Sichern und Wiederherstellen der Konfiguration von PSTN-Gateways erhalten Sie vom jeweiligen Hersteller.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="6a5d9-212">**Nebeneinander vorhandene Versionen von lync Server oder Office Communications Server**   Wenn Ihre lync Server 2013-Bereitstellung mit lync Server 2010 oder einer früheren Version von Office Communications Server koexistiert, können Sie die Verfahren in diesem Dokument nicht zum Sichern oder Wiederherstellen der früheren Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="6a5d9-213">Stattdessen müssen Sie die speziell für Ihre frühere Version dokumentierten Sicherungs- und Wiederherstellungsverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="6a5d9-214">Ausführliche Informationen zum Sichern und Wiederherstellen von lync Server 2010 finden Sie [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) unter.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-214">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="6a5d9-215">Ausführliche Informationen zum Sichern und Wiederherstellen von Microsoft Office Communications Server 2007 R2 finden Sie [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162)unter.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="6a5d9-216">**Infrastruktur Informationen**   Sie müssen Informationen zu Ihrer Infrastruktur sichern, beispielsweise Ihre Firewall-Konfiguration, Lastenausgleichskonfiguration, Internet Information Services (IIS) Konfiguration, Domain Name System (DNS) Datensätzen und IP-Adressen sowie die DHCP-Konfiguration (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="6a5d9-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="6a5d9-217">Ausführliche Informationen zum Sichern dieser Komponenten erhalten Sie vom jeweiligen Hersteller.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="6a5d9-218">**Microsoft Exchange und Exchange Unified Messaging (um)**   Sicherung und Wiederherstellung Microsoft Exchange und Exchange um wie in der Microsoft Exchange Dokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="6a5d9-219">Ausführliche Informationen zum Sichern und Wiederherstellen von Exchange Server 2013 finden Sie [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384)unter.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-219">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="6a5d9-220">Ausführliche Informationen zum Sichern und Wiederherstellen von Exchange Server 2010 finden Sie [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179)unter.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-220">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="6a5d9-221">Beachten Sie, dass lync Server 2013 die Möglichkeit bietet, Benutzer Kontaktlisten, hochauflösende Benutzer Fotos und in Exchange 2013 gespeicherte Archivdaten zu haben.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="6a5d9-222">In der folgenden Liste finden Sie Informationen zum Sichern dieser Datentypen:</span><span class="sxs-lookup"><span data-stu-id="6a5d9-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="6a5d9-223">**Hochauflösende Fotos** werden im Rahmen der Exchange Server Sicherung gesichert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="6a5d9-224">In lync Server 2013 wird ein **einheitlicher Kontaktspeicher** eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="6a5d9-225">Mit dem einheitlichen Kontaktspeicher können Benutzer alle Ihre Kontaktinformationen in Exchange 2013 speichern.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="6a5d9-226">Sie sollten sicherstellen, dass Sicherungen für Benutzer auf dem neuesten Stand sind, ob Ihre Benutzer Kontakte im einheitlichen Kontaktspeicher oder auf dem lync-Back-End-Server gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="6a5d9-227">In den folgenden Szenarien wird veranschaulicht, wo das Migrieren von Benutzerkontakten zum einheitlichen Kontaktspeicher zu Problemen beim Sicherungs-und Wiederherstellungsvorgang führen kann.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="6a5d9-228">**Szenario 1:** Benutzer Kontakte werden zum einheitlichen Kontaktspeicher migriert, und eine Wiederherstellung erfolgt über eine lync Server Sicherung, die vor der Migration von Benutzerkontakten durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="6a5d9-229">In diesem Szenario verfügt der Benutzer über einen Status veralteter Kontakte für bis zu einem Tag, bis lync Server Migrations Task die Migration von Benutzerkontakten zu Exchange beginnt.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="6a5d9-230">(Beachten Sie, dass die Exchange-Kontaktinformationen verwendet werden, da die Benutzer Kontakte zuvor zum einheitlichen Kontaktspeicher migriert wurden).</span><span class="sxs-lookup"><span data-stu-id="6a5d9-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="6a5d9-231">In diesem Szenario ist kein Administratoreingriff erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="6a5d9-232">**Szenario 2:** Benutzer Kontakte wurden zuvor im einheitlichen Kontaktspeicher gespeichert, dann jedoch zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="6a5d9-233">Eine Wiederherstellung wird von einer lync Server Sicherung durchgeführt, die ausgeführt wurde, als die Benutzer Kontakte im einheitlichen Kontaktspeicher gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="6a5d9-234">In diesem Szenario zeigt eine Fehlermeldung von `Error: Incorrect Exchange Version` in den Client-oder Lyss-Serverprotokollen möglicherweise dies als Problem an.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="6a5d9-235">Der Benutzer kann direkt in Exchange auf seine Kontaktliste in lync 2013 zugreifen, der Status des Clients stimmt jedoch nicht mit dem lync Server Zustand überein.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="6a5d9-236">Um dies zu beheben, muss ein Administrator die **Invoke-CsUCSRollback-** Cmdlets für die betroffenen Benutzer ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="6a5d9-237">**Archivierungsdaten** können in Exchange 2013 gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="6a5d9-238">Diese Daten sind für lync Server nicht wichtig, aber Sie können für Ihre Organisation für regulatorische Zwecke von entscheidender Bedeutung sein.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="6a5d9-239">Wenn Archivierungsdaten in Exchange gespeichert werden und für Ihre Organisation wichtig sind, folgen Sie den Exchange-Sicherungs-und Wiederherstellungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="6a5d9-240">Beachten Sie, dass die in Exchange gespeicherten Archivierungsdaten nicht wieder in lync Server verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="6a5d9-241">Darüber hinaus gibt es keine Möglichkeit, bereits in der lync-Archivierungsdatenbank gespeicherte Daten in Exchange zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

