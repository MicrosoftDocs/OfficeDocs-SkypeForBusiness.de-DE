---
title: 'Lync Server 2013: Platzierung von Daten und Protokolldateien SQL Server'
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
ms.openlocfilehash: 3f536f2d67010856259abf6b98936cd9e096fc93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509622"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="249ee-102">SQL Server der Daten-und Protokolldatei Platzierung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="249ee-102">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="249ee-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="249ee-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="249ee-104">Bei der Planung und Bereitstellung von Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2 SP1 für Ihre lync Server 2013 Front-End-Pool, ist es wichtig, dass Daten und Protokolldateien für die Leistung auf physischen Festplatten platziert werden.</span><span class="sxs-lookup"><span data-stu-id="249ee-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="249ee-105">Die empfohlene Datenträgerkonfiguration besteht in der Implementierung eines 1 +1-RAID-Satzes mit 6 Spindeln.</span><span class="sxs-lookup"><span data-stu-id="249ee-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="249ee-106">Wenn Sie alle Datenbank-und Protokolldateien, die von der Front-End-Pool und den zugehörigen Serverrollen und-Diensten verwendet werden (also Archivierungs-und Monitoring Server, lync Server Reaktionsgruppendienst, lync Server Dienst zum Parken von Anrufen) auf dem RAID-Laufwerk mit dem lync Server-Bereitstellungs-Assistenten platzieren, wird eine Konfiguration mit einer guten Leistung getestet.</span><span class="sxs-lookup"><span data-stu-id="249ee-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="249ee-107">Die Datenbankdateien und deren Verantwortlichkeiten sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="249ee-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="249ee-108">Wenn für Ihre Richtlinien und SQL Server Konfigurationen eine speziellere Installation erforderlich ist, können die Datenbank-und Protokolldateien mithilfe der lync Server-Verwaltungsshell an einem beliebigen vordefinierten Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="249ee-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="249ee-109">Weitere Informationen finden Sie unter <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Datenbankinstallation mit lync Server-Verwaltungsshell in lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="249ee-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="249ee-110">Daten- und Protokolldateien für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="249ee-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="249ee-111">Datenbankdateien des zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="249ee-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="249ee-112">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="249ee-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="249ee-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-114">Transaktionsprotokolldatei für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="249ee-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-115">XDS. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-116">Verwaltet die Konfiguration der aktuellen lync Server 2013 Topologie, wie Sie vom Topologie-Generator definiert und veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="249ee-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-117">LIS. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-118">Standortinformationsdienst-Datendatei</span><span class="sxs-lookup"><span data-stu-id="249ee-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-119">LIS. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-120">Transaktionsprotokoll für die Standortinformationsdienst-Datendatei</span><span class="sxs-lookup"><span data-stu-id="249ee-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="249ee-121">Daten- und Protokolldateien für Benutzer, Konferenzen und Adressbuch</span><span class="sxs-lookup"><span data-stu-id="249ee-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="249ee-122">Kern lync Server 2013-Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="249ee-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="249ee-123">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="249ee-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="249ee-124">RTC. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-125">Persistente Benutzerdaten (beispielsweise Zugriffssteuerungslisten (Access Control Lists, ACLs), Kontakte, geplante Konferenzen)</span><span class="sxs-lookup"><span data-stu-id="249ee-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-127">Transaktionsprotokoll für RTC-Daten</span><span class="sxs-lookup"><span data-stu-id="249ee-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-128">RTCDyn. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-129">Verwaltet transiente Benutzerdaten (Anwesenheits Laufzeitdaten)</span><span class="sxs-lookup"><span data-stu-id="249ee-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-131">Transaktionsprotokoll für RTCDyn-Daten</span><span class="sxs-lookup"><span data-stu-id="249ee-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-132">RTCAb. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-133">Die RTC-Adressbuchdatenbank (Real-Time Communications) ist das SQL Server-Repository, in dem Informationen des Adressbuchdiensts gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="249ee-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-134">RTCAb. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-135">Transaktionsprotokoll für den Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="249ee-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="249ee-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="249ee-137">Hostet das Konferenzverzeichnis</span><span class="sxs-lookup"><span data-stu-id="249ee-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-138">"Rtcxds". mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-139">Verwaltet die Sicherung für Benutzerdaten.</span><span class="sxs-lookup"><span data-stu-id="249ee-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-140">"Rtcxds". ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-141">Transaktionsprotokoll für "rtcxds"-Daten</span><span class="sxs-lookup"><span data-stu-id="249ee-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="249ee-142">Daten- und Protokolldateien für das Parken von Anrufen und Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="249ee-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="249ee-143">Anwendungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="249ee-143">Application database</span></span></th>
<th><span data-ttu-id="249ee-144">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="249ee-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="249ee-145">Cpsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-146">Dynamische Informationsdatenbank für den Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="249ee-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-148">Transaktionsprotokoll für Anwendung zum Parken von Anrufen Datendatei</span><span class="sxs-lookup"><span data-stu-id="249ee-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-149">Rgsconfig. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-150">Datendatei für den Lync Server-Reaktionsgruppendienst zur Konfiguration der Dienste</span><span class="sxs-lookup"><span data-stu-id="249ee-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-152">Transaktionsprotokolldatei für die Reaktionsgruppenanwendung Konfiguration</span><span class="sxs-lookup"><span data-stu-id="249ee-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-153">Rgsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-154">Datendatei des Reaktionsgruppendiensts für Laufzeitoperationen</span><span class="sxs-lookup"><span data-stu-id="249ee-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-156">Transaktionsprotokoll für die Laufzeitdatendatei des Reaktionsgruppendiensts</span><span class="sxs-lookup"><span data-stu-id="249ee-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="249ee-157">Daten- und Protokolldateien für den Archivierungs- und Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="249ee-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="249ee-158">Datenbankdateien für Archivierung und Überwachung</span><span class="sxs-lookup"><span data-stu-id="249ee-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="249ee-159">Zweck der Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="249ee-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="249ee-160">LcsCdr. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-161">Datenspeicher für den CdR-Prozess (Call Detail Recording) des Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="249ee-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-163">Transaktionsprotokoll für KDS-Daten</span><span class="sxs-lookup"><span data-stu-id="249ee-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-164">QoEMetrics. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-165">Von der Monitoring Server gespeicherte Quality of Experience-Datendatei</span><span class="sxs-lookup"><span data-stu-id="249ee-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-167">Transaktionsprotokoll für Überwachungsdaten</span><span class="sxs-lookup"><span data-stu-id="249ee-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249ee-168">Lcslog. mdf</span><span class="sxs-lookup"><span data-stu-id="249ee-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="249ee-169">Datendatei für die Aufbewahrung von Instant Messaging-und Konferenzdaten auf einem Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="249ee-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249ee-170">Lcslog. ldf</span><span class="sxs-lookup"><span data-stu-id="249ee-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="249ee-171">Transaktionsprotokoll für Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="249ee-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="249ee-p103">In diesem Thema wird auf Datenträger und RAID-Sätze verwiesen. Bei der Konfiguration von SQL Server-Ressourcen bezieht sich der Begriff "Datenträger" auf ein einzelnes Hardwaregerät. Ein Festplattenlaufwerk mit zwei Partitionen (je eine Partition für Protokoll- und Datendateien) ist nicht dasselbe wie zwei Datenträger, die als zwei dedizierte Komponenten für Protokoll- bzw. Datendateien eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="249ee-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="249ee-175">Bei RAID-Sätzen sind unterschiedliche RAID-Technologien von verschiedenen Anbietern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="249ee-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="249ee-176">Und mit dem verstärkten Einsatz von SANs (Storage Area Networks) werden dedizierte RAID-Sätze für ein einzelnes System seltener.</span><span class="sxs-lookup"><span data-stu-id="249ee-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="249ee-177">Sie sollten sich mit Ihrem RAID-oder SAN-Anbieter beraten lassen, um festzustellen, welche Konfiguration für das Datenträgerlayout am besten geeignet ist, wenn Sie für SQL Server Leistung mit lync Server 2013 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="249ee-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="249ee-178">Beachten Sie, dass nicht alle Festplattenlaufwerke identisch gefertigt werden, sodass einige Laufwerke eine bessere Leistung bieten als andere.</span><span class="sxs-lookup"><span data-stu-id="249ee-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="249ee-179">Selbst bei Laufwerken eines Herstellers kann die Leistung aufgrund von Drehgeschwindigkeit, Größe des Hardwarezwischenspeichers und anderen Faktoren variieren.</span><span class="sxs-lookup"><span data-stu-id="249ee-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

