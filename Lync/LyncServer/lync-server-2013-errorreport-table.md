---
title: 'Lync Server 2013: errorreport-Tabelle'
description: 'Lync Server 2013: errorreport-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572011"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="2784e-103">ErrorReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2784e-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2784e-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2784e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2784e-105">In der errorreport-Tabelle werden Informationen zu aufgetretenen Fehlern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2784e-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="2784e-106">Bei jedem Datensatz handelt es sich um ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="2784e-106">Each record is one error occurrence.</span></span> <span data-ttu-id="2784e-107">Die Fehler werden entweder von dem auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="2784e-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2784e-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="2784e-108">Column</span></span></th>
<th><span data-ttu-id="2784e-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2784e-109">Data Type</span></span></th>
<th><span data-ttu-id="2784e-110">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="2784e-110">Key/Index</span></span></th>
<th><span data-ttu-id="2784e-111">Details</span><span class="sxs-lookup"><span data-stu-id="2784e-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2784e-112"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="2784e-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="2784e-114">Primary</span><span class="sxs-lookup"><span data-stu-id="2784e-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="2784e-115">Datum und Uhrzeit, zu der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2784e-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-117">int</span><span class="sxs-lookup"><span data-stu-id="2784e-117">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-118">Primary</span><span class="sxs-lookup"><span data-stu-id="2784e-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="2784e-119">ID-Nummer zum Identifizieren des Fehlerberichts.</span><span class="sxs-lookup"><span data-stu-id="2784e-119">ID number to identify the error report.</span></span> <span data-ttu-id="2784e-120">Wird in Verbindung mit <strong>Fehler</strong> Zeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2784e-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-121"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-122">int</span><span class="sxs-lookup"><span data-stu-id="2784e-122">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-124">Eindeutige ID des Fehlertyps.</span><span class="sxs-lookup"><span data-stu-id="2784e-124">Unique ID of the error type.</span></span> <span data-ttu-id="2784e-125">Weitere Informationen finden Sie <a href="lync-server-2013-errordef-table.md">in der ErrorDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-127">int</span><span class="sxs-lookup"><span data-stu-id="2784e-127">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-129">Benutzer, der die Anforderung stammt, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="2784e-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="2784e-130">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-131"><strong>Touser-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-132">int</span><span class="sxs-lookup"><span data-stu-id="2784e-132">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-133">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-134">Zielbenutzer für die Anforderung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="2784e-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="2784e-135">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-137">int</span><span class="sxs-lookup"><span data-stu-id="2784e-137">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-138">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-139">Konferenz-URI im Zusammenhang mit dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="2784e-139">Conference URI related to the error.</span></span> <span data-ttu-id="2784e-140">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="2784e-141">Wenn ConferenceUriId nicht NULL ist, wird in der Regel entweder FromUserId oder touser-Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="2784e-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-142"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-143">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="2784e-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="2784e-144">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-145">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2784e-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2784e-146">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-148">int</span><span class="sxs-lookup"><span data-stu-id="2784e-148">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-149">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-150">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2784e-150">ID number to identify the session.</span></span> <span data-ttu-id="2784e-151">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2784e-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2784e-152">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-154">int</span><span class="sxs-lookup"><span data-stu-id="2784e-154">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-155">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-156">Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird).</span><span class="sxs-lookup"><span data-stu-id="2784e-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="2784e-157">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2784e-158">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2784e-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-160">int</span><span class="sxs-lookup"><span data-stu-id="2784e-160">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-162">Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird).</span><span class="sxs-lookup"><span data-stu-id="2784e-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="2784e-163">Weitere Informationen finden Sie <a href="lync-server-2013-application-table.md">in der Anwendungstabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2784e-164">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2784e-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-166">Abbildung</span><span class="sxs-lookup"><span data-stu-id="2784e-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2784e-167">Weitere Informationen zum Fehler.</span><span class="sxs-lookup"><span data-stu-id="2784e-167">More information about the error.</span></span></p>
<p><span data-ttu-id="2784e-168">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="2784e-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-170">int</span><span class="sxs-lookup"><span data-stu-id="2784e-170">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-171">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-172">Die Client Version des Endpunkts, der den Fehlerbericht sendet.</span><span class="sxs-lookup"><span data-stu-id="2784e-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="2784e-173">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2784e-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-175">Bit</span><span class="sxs-lookup"><span data-stu-id="2784e-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2784e-176">Ist der Fehlerbericht, der vom auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2784e-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-177"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-178">smallint</span><span class="sxs-lookup"><span data-stu-id="2784e-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2784e-179">Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="2784e-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-180"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-181">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="2784e-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2784e-182">Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="2784e-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="2784e-183">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2784e-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-184"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-185">int</span><span class="sxs-lookup"><span data-stu-id="2784e-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2784e-186">Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="2784e-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="2784e-187">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2784e-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2784e-188"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-189">int</span><span class="sxs-lookup"><span data-stu-id="2784e-189">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-190">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-191">Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.</span><span class="sxs-lookup"><span data-stu-id="2784e-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2784e-192"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="2784e-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="2784e-193">int</span><span class="sxs-lookup"><span data-stu-id="2784e-193">int</span></span></p></td>
<td><p><span data-ttu-id="2784e-194">Fremd</span><span class="sxs-lookup"><span data-stu-id="2784e-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2784e-195">Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2784e-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

