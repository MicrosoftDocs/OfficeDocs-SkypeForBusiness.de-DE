---
title: 'Lync Server 2013: Platzierung von SQL Server-Daten und Protokolldatei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="51b1e-102">Platzierung von SQL Server-Daten und Protokolldatei für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51b1e-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51b1e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="51b1e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="51b1e-104">Bei der Planung und Bereitstellung von Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2 SP1 für Ihren lync Server 2013-Front-End-Pool ist es wichtig, dass Daten und Protokolldateien auf physischen Festplatten zur Leistung platziert werden.</span><span class="sxs-lookup"><span data-stu-id="51b1e-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="51b1e-105">Die empfohlene Festplattenkonfiguration besteht in der Implementierung eines 1 +1-RAID-Satzes mit 6 Spindeln.</span><span class="sxs-lookup"><span data-stu-id="51b1e-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="51b1e-106">Platzieren aller vom Front-End-Pool verwendeten Datenbank-und Protokolldateien und der zugehörigen Serverrollen und Dienste (also Archivierungs-und Überwachungsserver, lync Server-Reaktionsgruppendienst, lync Server-Anruf Park Dienst) auf dem RAID-Laufwerk, das mit dem lync-Server festgesetzt wird Der Bereitstellungs-Assistent führt zu einer Konfiguration, die auf eine gute Leistung getestet wurde.</span><span class="sxs-lookup"><span data-stu-id="51b1e-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="51b1e-107">Die Datenbankdateien und deren Verantwortlichkeiten sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="51b1e-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51b1e-108">Wenn für Ihre Richtlinien und SQL Server-Konfigurationen eine spezialisiertere Installation erforderlich ist, können die Datenbank-und Protokolldateien mithilfe der lync Server-Verwaltungsshell an einem beliebigen vordefinierten Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="51b1e-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="51b1e-109">Weitere Informationen finden Sie unter <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Datenbankinstallation mithilfe der lync Server-Verwaltungsshell in lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="51b1e-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="51b1e-110">Daten-und Protokolldateien für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="51b1e-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51b1e-111">Zentrale Verwaltungsspeicher-Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="51b1e-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="51b1e-112">Datendatei oder Protokoll Zweck</span><span class="sxs-lookup"><span data-stu-id="51b1e-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-114">Transaktionsprotokolldatei für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="51b1e-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-115">XDS. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-116">Verwaltet die Konfiguration der aktuellen lync Server 2013-Topologie, wie Sie vom Topologie-Generator definiert und veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="51b1e-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-117">LIS. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-118">Datendatei des Standort Informationsdiensts</span><span class="sxs-lookup"><span data-stu-id="51b1e-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-119">LIS. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-120">Transaktionsprotokoll für die Datendatei des Standort Informationsdiensts</span><span class="sxs-lookup"><span data-stu-id="51b1e-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="51b1e-121">Daten-und Protokolldateien für Benutzer, Konferenz und Adressbuch</span><span class="sxs-lookup"><span data-stu-id="51b1e-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51b1e-122">Core lync Server 2013-Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="51b1e-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="51b1e-123">Datendatei oder Protokoll Zweck</span><span class="sxs-lookup"><span data-stu-id="51b1e-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-124">RTC. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-125">Beständige Benutzerdaten (beispielsweise Zugriffssteuerungslisten (ACLs), Kontakte, geplante Konferenzen)</span><span class="sxs-lookup"><span data-stu-id="51b1e-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-127">Transaktionsprotokoll für RTC-Daten</span><span class="sxs-lookup"><span data-stu-id="51b1e-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-128">RTCDyn. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-129">Pflegt vorübergehende Benutzerdaten (Anwesenheits Laufzeitdaten)</span><span class="sxs-lookup"><span data-stu-id="51b1e-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-131">Transaktionsprotokoll für RTCDyn-Daten</span><span class="sxs-lookup"><span data-stu-id="51b1e-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-132">RTCAb. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-133">RTC-Adressbuchdatenbank (Echtzeitkommunikation) ist das SQL Server-Repository, in dem Adressbuchdienst Informationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="51b1e-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-134">RTCAb. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-135">Transaktionsprotokoll für Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="51b1e-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="51b1e-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="51b1e-137">Gastgeber des Konferenz Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="51b1e-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-138">Rtcxds. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-139">Verwaltet die Sicherung für Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="51b1e-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-141">Transaktionsprotokoll für Rtcxds-Daten</span><span class="sxs-lookup"><span data-stu-id="51b1e-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="51b1e-142">Daten-und Protokolldateien für den Anruf Park und die Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="51b1e-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51b1e-143">Anwendungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="51b1e-143">Application database</span></span></th>
<th><span data-ttu-id="51b1e-144">Datendatei oder Protokoll Zweck</span><span class="sxs-lookup"><span data-stu-id="51b1e-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-145">Cpsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-146">Dynamische Informationsdatenbank für die Anwendung "Parken des Anrufs"</span><span class="sxs-lookup"><span data-stu-id="51b1e-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-148">Transaktionsprotokoll für die APP-Datendatei des Anruf Parks</span><span class="sxs-lookup"><span data-stu-id="51b1e-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-149">Rgsconfig. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-150">Lync Server Response Group Service-Datendatei für die Konfiguration der Dienste</span><span class="sxs-lookup"><span data-stu-id="51b1e-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-152">Transaktionsprotokolldatei für die Anwendungskonfiguration der Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="51b1e-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-153">Rgsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-154">Datendatei des Reaktionsgruppendiensts für Laufzeitvorgänge</span><span class="sxs-lookup"><span data-stu-id="51b1e-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-156">Transaktionsprotokoll für die Datendatei der Reaktionsgruppendienst-Laufzeit</span><span class="sxs-lookup"><span data-stu-id="51b1e-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="51b1e-157">Daten-und Protokolldateien für Archivierungs-und Überwachungs Server</span><span class="sxs-lookup"><span data-stu-id="51b1e-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51b1e-158">Archivieren und Überwachen von Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="51b1e-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="51b1e-159">Datendatei oder Protokoll Zweck</span><span class="sxs-lookup"><span data-stu-id="51b1e-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-160">LcsCdr. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-161">Datenspeicher für den Prozess der Anrufdetailaufzeichnung (CDR) des Überwachungsservers</span><span class="sxs-lookup"><span data-stu-id="51b1e-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-163">Transaktionslog für Daten zur Anrufdetailaufzeichnung (CDR)</span><span class="sxs-lookup"><span data-stu-id="51b1e-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-164">Datenbank QoEMetrics werden. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-165">Auf dem Überwachungs Server gespeicherte Datendatei mit hoher Qualität</span><span class="sxs-lookup"><span data-stu-id="51b1e-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-166">Datenbank QoEMetrics werden. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-167">Transaktionslog zum Überwachen von Daten</span><span class="sxs-lookup"><span data-stu-id="51b1e-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51b1e-168">Lcslog. mdf</span><span class="sxs-lookup"><span data-stu-id="51b1e-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-169">Datendatei zur Aufbewahrung von Sofortnachrichten und Konferenzdaten auf einem Archivierungs Server</span><span class="sxs-lookup"><span data-stu-id="51b1e-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51b1e-170">Lcslog. ldf</span><span class="sxs-lookup"><span data-stu-id="51b1e-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="51b1e-171">Transaktionsprotokoll zum Archivieren von Daten</span><span class="sxs-lookup"><span data-stu-id="51b1e-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="51b1e-172">In diesem Thema werden Verweise auf die Festplatte und auf RAID festgesetzt.</span><span class="sxs-lookup"><span data-stu-id="51b1e-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="51b1e-173">Beachten Sie, dass bei der Konfiguration von SQL Server-Ressourcen ein einzelnes Hardwaregerät auf einen Datenträger verweist.</span><span class="sxs-lookup"><span data-stu-id="51b1e-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="51b1e-174">Ein Festplattenlaufwerk mit zwei Partitionen, einem Protokolldateien und der anderen Partition, in der Datendateien gespeichert sind, ist nicht mit zwei Festplatten identisch, die jeweils für Protokoll-oder Datendateien reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="51b1e-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="51b1e-175">In Bezug auf RAID-Sets gibt es eine Reihe unterschiedlicher RAID-Technologien verschiedener Anbieter.</span><span class="sxs-lookup"><span data-stu-id="51b1e-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="51b1e-176">Und mit der Verbreitung von San (Storage Area Networks) sind RAID-Sätze, die einem einzigen System gewidmet sind, seltener.</span><span class="sxs-lookup"><span data-stu-id="51b1e-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="51b1e-177">Wenden Sie sich an Ihren RAID-oder SAN-Anbieter, um zu ermitteln, welche Konfiguration für das Festplattenlayout am besten geeignet ist, wenn Sie die Leistung von SQL Server mit lync Server 2013 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="51b1e-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="51b1e-178">Beachten Sie auch, dass nicht alle Festplatten gleichermaßen erstellt werden. einige funktionieren besser als andere.</span><span class="sxs-lookup"><span data-stu-id="51b1e-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="51b1e-179">Auch Laufwerke desselben Herstellers können aufgrund von Drehzahl, Hardwarecache Größe und anderen Faktoren in der Leistung variieren.</span><span class="sxs-lookup"><span data-stu-id="51b1e-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

