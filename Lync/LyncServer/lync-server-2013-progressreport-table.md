---
title: 'Lync Server 2013: ProgressReport-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="37aca-102">ProgressReport-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37aca-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37aca-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="37aca-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="37aca-104">Statusberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung an die Datenbank hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="37aca-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="37aca-105">Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von lync Server 2013 für diagnostische Zwecke nützlich sein können.</span><span class="sxs-lookup"><span data-stu-id="37aca-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="37aca-106">Die Felder "Fehler", "ErrorReportSeq" und "ProgressReportSeq" beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von anrufen oder Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="37aca-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37aca-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="37aca-107">Column</span></span></th>
<th><span data-ttu-id="37aca-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="37aca-108">Data Type</span></span></th>
<th><span data-ttu-id="37aca-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="37aca-109">Key/Index</span></span></th>
<th><span data-ttu-id="37aca-110">Details</span><span class="sxs-lookup"><span data-stu-id="37aca-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37aca-111"><strong>Fehlerzeit</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-112">datetime</span><span class="sxs-lookup"><span data-stu-id="37aca-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="37aca-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="37aca-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37aca-114">Datum und Uhrzeit des Status Fehlerberichts, der diesen Statusbericht enthält.</span><span class="sxs-lookup"><span data-stu-id="37aca-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="37aca-115">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="37aca-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37aca-116"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-117">int</span><span class="sxs-lookup"><span data-stu-id="37aca-117">int</span></span></p></td>
<td><p><span data-ttu-id="37aca-118">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="37aca-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37aca-119">ID-Nummer, die in Verbindung mit Fehlerzeit verwendet wird, ProgressReportSeq, um einen Statusbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="37aca-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="37aca-120">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="37aca-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37aca-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-122">int</span><span class="sxs-lookup"><span data-stu-id="37aca-122">int</span></span></p></td>
<td><p><span data-ttu-id="37aca-123">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="37aca-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37aca-124">Die ID-Nummer, die den Fehlerbericht identifiziert.</span><span class="sxs-lookup"><span data-stu-id="37aca-124">ID number that identifies the error report.</span></span> <span data-ttu-id="37aca-125">ErrorReporSeq wird in Verbindung mit Fehlerzeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="37aca-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="37aca-126">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="37aca-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="37aca-127">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37aca-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37aca-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-129">int</span><span class="sxs-lookup"><span data-stu-id="37aca-129">int</span></span></p></td>
<td><p><span data-ttu-id="37aca-130">Primary</span><span class="sxs-lookup"><span data-stu-id="37aca-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="37aca-131">Die ID-Nummer zur Identifizierung des Statusberichts.</span><span class="sxs-lookup"><span data-stu-id="37aca-131">ID number to identify the progress report.</span></span> <span data-ttu-id="37aca-132">Wird in Verbindung mit Fehlerzeit und ErrorReportSeq verwendet, um einen Statusbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="37aca-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37aca-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-134">int</span><span class="sxs-lookup"><span data-stu-id="37aca-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37aca-135">Diagnose-ID des Statusberichts</span><span class="sxs-lookup"><span data-stu-id="37aca-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="37aca-136">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37aca-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37aca-137"><strong>SourceID</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-138">int</span><span class="sxs-lookup"><span data-stu-id="37aca-138">int</span></span></p></td>
<td><p><span data-ttu-id="37aca-139">Fremd</span><span class="sxs-lookup"><span data-stu-id="37aca-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37aca-140">Der Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="37aca-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="37aca-141">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> . Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37aca-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37aca-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-143">int</span><span class="sxs-lookup"><span data-stu-id="37aca-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37aca-144">Der lync-Server Prozess, zu dem der Bericht gehört.</span><span class="sxs-lookup"><span data-stu-id="37aca-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="37aca-145">Weitere Informationen finden Sie in der Anwendungstabelle.</span><span class="sxs-lookup"><span data-stu-id="37aca-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37aca-146"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-147">Bild</span><span class="sxs-lookup"><span data-stu-id="37aca-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37aca-148">Details des Statusberichts, die im Binärformat gespeichert werden, um Platz zu sparen. Diese Daten können mit dieser Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="37aca-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="37aca-149">Umwandlung (Umwandlung (Detail als varbinary (max)) als varchar (max))</span><span class="sxs-lookup"><span data-stu-id="37aca-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37aca-150"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="37aca-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37aca-152">Eindeutiger Bezeichner, der die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="37aca-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="37aca-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37aca-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37aca-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="37aca-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37aca-155">int</span><span class="sxs-lookup"><span data-stu-id="37aca-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37aca-156">Zeit (in Millisekunden) für eine bestimmte Komponente, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="37aca-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="37aca-157">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37aca-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

