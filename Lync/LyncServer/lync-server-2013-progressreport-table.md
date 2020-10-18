---
title: 'Lync Server 2013: ProgressReport-Tabelle'
description: 'Lync Server 2013: ProgressReport-Tabelle.'
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
ms.openlocfilehash: d36ee2ab75410ea2462da4b647ef5b45afefb1bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579821"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="00a07-103">ProgressReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a07-103">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00a07-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="00a07-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="00a07-105">Fortschrittsberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung in die Datenbank hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="00a07-105">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="00a07-106">Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt.</span><span class="sxs-lookup"><span data-stu-id="00a07-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="00a07-107">Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="00a07-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00a07-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="00a07-108">Column</span></span></th>
<th><span data-ttu-id="00a07-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="00a07-109">Data Type</span></span></th>
<th><span data-ttu-id="00a07-110">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="00a07-110">Key/Index</span></span></th>
<th><span data-ttu-id="00a07-111">Details</span><span class="sxs-lookup"><span data-stu-id="00a07-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00a07-112"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="00a07-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="00a07-114">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="00a07-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="00a07-115">Datum und Uhrzeit des Fortschritts Fehlerberichts, der diesen Fortschrittsbericht enthält.</span><span class="sxs-lookup"><span data-stu-id="00a07-115">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="00a07-116">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00a07-116">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a07-117"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-117"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-118">int</span><span class="sxs-lookup"><span data-stu-id="00a07-118">int</span></span></p></td>
<td><p><span data-ttu-id="00a07-119">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="00a07-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="00a07-120">ID-Nummer, die in Verbindung mit Error-ProgressReportSeq verwendet wird, um einen Statusbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00a07-120">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="00a07-121">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00a07-121">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00a07-122"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-122"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-123">int</span><span class="sxs-lookup"><span data-stu-id="00a07-123">int</span></span></p></td>
<td><p><span data-ttu-id="00a07-124">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="00a07-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="00a07-125">ID-Nummer, die den Fehlerbericht identifiziert.</span><span class="sxs-lookup"><span data-stu-id="00a07-125">ID number that identifies the error report.</span></span> <span data-ttu-id="00a07-126">ErrorReporSeq wird in Verbindung mit Fehlerzeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00a07-126">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="00a07-127">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00a07-127">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="00a07-128">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00a07-128">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a07-129"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-129"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-130">int</span><span class="sxs-lookup"><span data-stu-id="00a07-130">int</span></span></p></td>
<td><p><span data-ttu-id="00a07-131">Primary</span><span class="sxs-lookup"><span data-stu-id="00a07-131">Primary</span></span></p></td>
<td><p><span data-ttu-id="00a07-p105">ID zur Identifikation des Fortschrittsberichts. Wird zusammen mit ErrorTime und ErrorReportSeq zur eindeutigen Identifikation eines Fortschrittsberichts verwendet.</span><span class="sxs-lookup"><span data-stu-id="00a07-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00a07-134"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-134"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-135">int</span><span class="sxs-lookup"><span data-stu-id="00a07-135">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00a07-136">Die Diagnose-ID des Fortschrittberichts.</span><span class="sxs-lookup"><span data-stu-id="00a07-136">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="00a07-137">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00a07-137">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a07-138"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-138"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-139">int</span><span class="sxs-lookup"><span data-stu-id="00a07-139">int</span></span></p></td>
<td><p><span data-ttu-id="00a07-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="00a07-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="00a07-141">Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="00a07-141">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="00a07-142">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> . Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00a07-142">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00a07-143"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-143"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-144">int</span><span class="sxs-lookup"><span data-stu-id="00a07-144">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00a07-p107">Der Lync Server-Vorgang, auf den sich der Bericht bezieht. Weitere Informationen finden Sie in der Anwendungstabelle.</span><span class="sxs-lookup"><span data-stu-id="00a07-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a07-147"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-147"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-148">Abbildung</span><span class="sxs-lookup"><span data-stu-id="00a07-148">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00a07-149">Einzelheiten über den Fortschrittsbericht, gespeichert im Binärformat, um Speicherplatz einzusparen. Diese Daten können mit der folgenden Syntax in ein Textformat konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="00a07-149">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="00a07-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="00a07-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00a07-151"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-151"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-152">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="00a07-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00a07-153">Eindeutige ID, die Informationen zum Zeitpunkt des Konferenzbeitritts für die verschiedenen an der Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="00a07-153">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="00a07-154">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00a07-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a07-155"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="00a07-155"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00a07-156">int</span><span class="sxs-lookup"><span data-stu-id="00a07-156">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00a07-157">Zeit (in Millisekunden) für den Konferenzbeitritt einer bestimmten Komponente.</span><span class="sxs-lookup"><span data-stu-id="00a07-157">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="00a07-158">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00a07-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

