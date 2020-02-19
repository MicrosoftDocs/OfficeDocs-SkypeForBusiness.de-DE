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
ms.openlocfilehash: 50697242b7086dbd81b74d098d200b1162ac12a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="7ed7f-102">ProgressReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed7f-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ed7f-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7ed7f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7ed7f-104">Fortschrittsberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung in die Datenbank hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="7ed7f-105">Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="7ed7f-106">Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ed7f-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="7ed7f-107">Column</span></span></th>
<th><span data-ttu-id="7ed7f-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7ed7f-108">Data Type</span></span></th>
<th><span data-ttu-id="7ed7f-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="7ed7f-109">Key/Index</span></span></th>
<th><span data-ttu-id="7ed7f-110">Details</span><span class="sxs-lookup"><span data-stu-id="7ed7f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ed7f-111"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="7ed7f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="7ed7f-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-114">Datum und Uhrzeit des Fortschritts Fehlerberichts, der diesen Fortschrittsbericht enthält.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="7ed7f-115">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ed7f-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed7f-116"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-117">int</span><span class="sxs-lookup"><span data-stu-id="7ed7f-117">int</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="7ed7f-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-119">ID-Nummer, die in Verbindung mit Error-ProgressReportSeq verwendet wird, um einen Statusbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="7ed7f-120">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ed7f-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed7f-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-122">int</span><span class="sxs-lookup"><span data-stu-id="7ed7f-122">int</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-123">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="7ed7f-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-124">ID-Nummer, die den Fehlerbericht identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-124">ID number that identifies the error report.</span></span> <span data-ttu-id="7ed7f-125">ErrorReporSeq wird in Verbindung mit Fehlerzeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="7ed7f-126">Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ed7f-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="7ed7f-127">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed7f-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-129">int</span><span class="sxs-lookup"><span data-stu-id="7ed7f-129">int</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-130">Primary</span><span class="sxs-lookup"><span data-stu-id="7ed7f-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-p105">ID zur Identifikation des Fortschrittsberichts. Wird zusammen mit ErrorTime und ErrorReportSeq zur eindeutigen Identifikation eines Fortschrittsberichts verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed7f-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-134">int</span><span class="sxs-lookup"><span data-stu-id="7ed7f-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ed7f-135">Die Diagnose-ID des Fortschrittberichts.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="7ed7f-136">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed7f-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-138">int</span><span class="sxs-lookup"><span data-stu-id="7ed7f-138">int</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-139">Fremd</span><span class="sxs-lookup"><span data-stu-id="7ed7f-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ed7f-140">Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="7ed7f-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="7ed7f-141">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> . Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed7f-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-143">int</span><span class="sxs-lookup"><span data-stu-id="7ed7f-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ed7f-p107">Der Lync Server-Vorgang, auf den sich der Bericht bezieht. Weitere Informationen finden Sie in der Anwendungstabelle.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed7f-146"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-147">Abbildung</span><span class="sxs-lookup"><span data-stu-id="7ed7f-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ed7f-148">Einzelheiten über den Fortschrittsbericht, gespeichert im Binärformat, um Speicherplatz einzusparen. Diese Daten können mit der folgenden Syntax in ein Textformat konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="7ed7f-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="7ed7f-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed7f-150"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="7ed7f-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ed7f-152">Eindeutige ID, die Informationen zum Zeitpunkt des Konferenzbeitritts für die verschiedenen an der Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="7ed7f-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed7f-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="7ed7f-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ed7f-155">int</span><span class="sxs-lookup"><span data-stu-id="7ed7f-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ed7f-156">Zeit (in Millisekunden) für den Konferenzbeitritt einer bestimmten Komponente.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="7ed7f-157">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7ed7f-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

