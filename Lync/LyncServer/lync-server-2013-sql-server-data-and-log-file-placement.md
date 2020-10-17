---
title: 'Lync Server 2013: Platzierung von Daten und Protokolldateien SQL Server'
description: 'Lync Server 2013: SQL Server der Daten-und Protokolldatei Platzierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a127254fec41a734136df9b63fc6cc8929745df7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558281"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="90986-103">SQL Server der Daten-und Protokolldatei Platzierung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90986-103">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90986-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="90986-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="90986-105">Bei der Planung und Bereitstellung von Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2 SP1 für Ihre lync Server 2013 Front-End-Pool, ist es wichtig, dass Daten und Protokolldateien für die Leistung auf physischen Festplatten platziert werden.</span><span class="sxs-lookup"><span data-stu-id="90986-105">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="90986-106">Die empfohlene Datenträgerkonfiguration besteht in der Implementierung eines 1 +1-RAID-Satzes mit 6 Spindeln.</span><span class="sxs-lookup"><span data-stu-id="90986-106">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="90986-107">Wenn Sie alle Datenbank-und Protokolldateien, die von der Front-End-Pool und den zugehörigen Serverrollen und-Diensten verwendet werden (also Archivierungs-und Monitoring Server, lync Server Reaktionsgruppendienst, lync Server Dienst zum Parken von Anrufen) auf dem RAID-Laufwerk mit dem lync Server-Bereitstellungs-Assistenten platzieren, wird eine Konfiguration mit einer guten Leistung getestet.</span><span class="sxs-lookup"><span data-stu-id="90986-107">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="90986-108">Die Datenbankdateien und deren Verantwortlichkeiten sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="90986-108">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90986-109">Wenn für Ihre Richtlinien und SQL Server Konfigurationen eine speziellere Installation erforderlich ist, können die Datenbank-und Protokolldateien mithilfe der lync Server-Verwaltungsshell an einem beliebigen vordefinierten Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="90986-109">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="90986-110">Weitere Informationen finden Sie unter <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Datenbankinstallation mit lync Server-Verwaltungsshell in lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="90986-110">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="90986-111">Daten- und Protokolldateien für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="90986-111">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90986-112">Datenbankdateien des zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="90986-112">Central Management store database files</span></span></th>
<th><span data-ttu-id="90986-113">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="90986-113">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90986-114">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-114">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-115">Transaktionsprotokolldatei für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="90986-115">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-116">XDS. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-116">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-117">Verwaltet die Konfiguration der aktuellen lync Server 2013 Topologie, wie Sie vom Topologie-Generator definiert und veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="90986-117">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-118">LIS. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-118">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-119">Standortinformationsdienst-Datendatei</span><span class="sxs-lookup"><span data-stu-id="90986-119">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-120">LIS. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-120">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-121">Transaktionsprotokoll für die Standortinformationsdienst-Datendatei</span><span class="sxs-lookup"><span data-stu-id="90986-121">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="90986-122">Daten- und Protokolldateien für Benutzer, Konferenzen und Adressbuch</span><span class="sxs-lookup"><span data-stu-id="90986-122">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90986-123">Kern lync Server 2013-Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="90986-123">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="90986-124">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="90986-124">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90986-125">RTC. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-125">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-126">Persistente Benutzerdaten (beispielsweise Zugriffssteuerungslisten (Access Control Lists, ACLs), Kontakte, geplante Konferenzen)</span><span class="sxs-lookup"><span data-stu-id="90986-126">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-127">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-127">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-128">Transaktionsprotokoll für RTC-Daten</span><span class="sxs-lookup"><span data-stu-id="90986-128">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-129">RTCDyn. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-129">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-130">Verwaltet transiente Benutzerdaten (Anwesenheits Laufzeitdaten)</span><span class="sxs-lookup"><span data-stu-id="90986-130">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-131">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-131">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-132">Transaktionsprotokoll für RTCDyn-Daten</span><span class="sxs-lookup"><span data-stu-id="90986-132">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-133">RTCAb. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-133">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-134">Die RTC-Adressbuchdatenbank (Real-Time Communications) ist das SQL Server-Repository, in dem Informationen des Adressbuchdiensts gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="90986-134">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-135">RTCAb. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-135">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-136">Transaktionsprotokoll für den Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="90986-136">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-137">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="90986-137">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="90986-138">Hostet das Konferenzverzeichnis</span><span class="sxs-lookup"><span data-stu-id="90986-138">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-139">"Rtcxds". mdf</span><span class="sxs-lookup"><span data-stu-id="90986-139">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-140">Verwaltet die Sicherung für Benutzerdaten.</span><span class="sxs-lookup"><span data-stu-id="90986-140">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-141">"Rtcxds". ldf</span><span class="sxs-lookup"><span data-stu-id="90986-141">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-142">Transaktionsprotokoll für "rtcxds"-Daten</span><span class="sxs-lookup"><span data-stu-id="90986-142">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="90986-143">Daten- und Protokolldateien für das Parken von Anrufen und Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="90986-143">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90986-144">Anwendungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="90986-144">Application database</span></span></th>
<th><span data-ttu-id="90986-145">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="90986-145">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90986-146">Cpsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-146">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-147">Dynamische Informationsdatenbank für den Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="90986-147">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-148">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-148">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-149">Transaktionsprotokoll für Anwendung zum Parken von Anrufen Datendatei</span><span class="sxs-lookup"><span data-stu-id="90986-149">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-150">Rgsconfig. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-150">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-151">Datendatei für den Lync Server-Reaktionsgruppendienst zur Konfiguration der Dienste</span><span class="sxs-lookup"><span data-stu-id="90986-151">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-152">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-152">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-153">Transaktionsprotokolldatei für die Reaktionsgruppenanwendung Konfiguration</span><span class="sxs-lookup"><span data-stu-id="90986-153">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-154">Rgsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-154">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-155">Datendatei des Reaktionsgruppendiensts für Laufzeitoperationen</span><span class="sxs-lookup"><span data-stu-id="90986-155">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-156">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-156">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-157">Transaktionsprotokoll für die Laufzeitdatendatei des Reaktionsgruppendiensts</span><span class="sxs-lookup"><span data-stu-id="90986-157">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="90986-158">Daten- und Protokolldateien für den Archivierungs- und Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="90986-158">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90986-159">Datenbankdateien für Archivierung und Überwachung</span><span class="sxs-lookup"><span data-stu-id="90986-159">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="90986-160">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="90986-160">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90986-161">LcsCdr. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-161">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-162">Datenspeicher für den CdR-Prozess (Call Detail Recording) des Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="90986-162">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-163">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-163">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-164">Transaktionsprotokoll für KDS-Daten</span><span class="sxs-lookup"><span data-stu-id="90986-164">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-165">QoEMetrics. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-165">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-166">Von der Monitoring Server gespeicherte Quality of Experience-Datendatei</span><span class="sxs-lookup"><span data-stu-id="90986-166">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-167">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-167">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-168">Transaktionsprotokoll für Überwachungsdaten</span><span class="sxs-lookup"><span data-stu-id="90986-168">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90986-169">Lcslog. mdf</span><span class="sxs-lookup"><span data-stu-id="90986-169">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="90986-170">Datendatei für die Aufbewahrung von Instant Messaging-und Konferenzdaten auf einem Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="90986-170">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90986-171">Lcslog. ldf</span><span class="sxs-lookup"><span data-stu-id="90986-171">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="90986-172">Transaktionsprotokoll für Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="90986-172">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90986-p103">In diesem Thema wird auf Datenträger und RAID-Sätze verwiesen. Bei der Konfiguration von SQL Server-Ressourcen bezieht sich der Begriff "Datenträger" auf ein einzelnes Hardwaregerät. Ein Festplattenlaufwerk mit zwei Partitionen (je eine Partition für Protokoll- und Datendateien) ist nicht dasselbe wie zwei Datenträger, die als zwei dedizierte Komponenten für Protokoll- bzw. Datendateien eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="90986-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="90986-176">Bei RAID-Sätzen sind unterschiedliche RAID-Technologien von verschiedenen Anbietern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="90986-176">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="90986-177">Und mit dem verstärkten Einsatz von SANs (Storage Area Networks) werden dedizierte RAID-Sätze für ein einzelnes System seltener.</span><span class="sxs-lookup"><span data-stu-id="90986-177">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="90986-178">Sie sollten sich mit Ihrem RAID-oder SAN-Anbieter beraten lassen, um festzustellen, welche Konfiguration für das Datenträgerlayout am besten geeignet ist, wenn Sie für SQL Server Leistung mit lync Server 2013 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="90986-178">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="90986-179">Beachten Sie, dass nicht alle Festplattenlaufwerke identisch gefertigt werden, sodass einige Laufwerke eine bessere Leistung bieten als andere.</span><span class="sxs-lookup"><span data-stu-id="90986-179">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="90986-180">Selbst bei Laufwerken eines Herstellers kann die Leistung aufgrund von Drehgeschwindigkeit, Größe des Hardwarezwischenspeichers und anderen Faktoren variieren.</span><span class="sxs-lookup"><span data-stu-id="90986-180">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

