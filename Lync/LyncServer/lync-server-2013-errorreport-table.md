---
title: 'Lync Server 2013: errorreport-Tabelle'
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
ms.openlocfilehash: 6c2a0b85e905bc7e00488c667a242965e169872b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="f59ba-102">ErrorReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f59ba-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f59ba-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f59ba-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f59ba-104">In der errorreport-Tabelle werden Informationen zu aufgetretenen Fehlern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f59ba-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="f59ba-105">Bei jedem Datensatz handelt es sich um ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="f59ba-105">Each record is one error occurrence.</span></span> <span data-ttu-id="f59ba-106">Die Fehler werden entweder von dem auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="f59ba-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f59ba-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="f59ba-107">Column</span></span></th>
<th><span data-ttu-id="f59ba-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f59ba-108">Data Type</span></span></th>
<th><span data-ttu-id="f59ba-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="f59ba-109">Key/Index</span></span></th>
<th><span data-ttu-id="f59ba-110">Details</span><span class="sxs-lookup"><span data-stu-id="f59ba-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-111"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f59ba-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f59ba-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f59ba-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f59ba-114">Datum und Uhrzeit, zu der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f59ba-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-116">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-116">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-117">Primary</span><span class="sxs-lookup"><span data-stu-id="f59ba-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f59ba-118">ID-Nummer zum Identifizieren des Fehlerberichts.</span><span class="sxs-lookup"><span data-stu-id="f59ba-118">ID number to identify the error report.</span></span> <span data-ttu-id="f59ba-119">Wird in Verbindung mit <strong>Fehler</strong> Zeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f59ba-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-120"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-121">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-121">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-123">Eindeutige ID des Fehlertyps.</span><span class="sxs-lookup"><span data-stu-id="f59ba-123">Unique ID of the error type.</span></span> <span data-ttu-id="f59ba-124">Weitere Informationen finden Sie <a href="lync-server-2013-errordef-table.md">in der ErrorDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-126">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-126">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-128">Benutzer, der die Anforderung stammt, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="f59ba-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="f59ba-129">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-130"><strong>Touser-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-131">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-131">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-132">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-133">Zielbenutzer für die Anforderung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="f59ba-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="f59ba-134">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-136">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-136">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-137">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-138">Konferenz-URI im Zusammenhang mit dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="f59ba-138">Conference URI related to the error.</span></span> <span data-ttu-id="f59ba-139">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f59ba-140">Wenn ConferenceUriId nicht NULL ist, wird in der Regel entweder FromUserId oder touser-Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="f59ba-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-141"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-142">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f59ba-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="f59ba-143">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-144">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f59ba-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f59ba-145">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-147">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-147">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-148">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-149">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f59ba-149">ID number to identify the session.</span></span> <span data-ttu-id="f59ba-150">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f59ba-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f59ba-151">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-153">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-153">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-154">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-155">Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird).</span><span class="sxs-lookup"><span data-stu-id="f59ba-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="f59ba-156">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f59ba-157">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f59ba-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-159">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-159">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-160">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-161">Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird).</span><span class="sxs-lookup"><span data-stu-id="f59ba-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="f59ba-162">Weitere Informationen finden Sie <a href="lync-server-2013-application-table.md">in der Anwendungstabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f59ba-163">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f59ba-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-165">Abbildung</span><span class="sxs-lookup"><span data-stu-id="f59ba-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f59ba-166">Weitere Informationen zum Fehler.</span><span class="sxs-lookup"><span data-stu-id="f59ba-166">More information about the error.</span></span></p>
<p><span data-ttu-id="f59ba-167">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="f59ba-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-169">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-169">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-170">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-171">Die Client Version des Endpunkts, der den Fehlerbericht sendet.</span><span class="sxs-lookup"><span data-stu-id="f59ba-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="f59ba-172">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f59ba-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-174">Bit</span><span class="sxs-lookup"><span data-stu-id="f59ba-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f59ba-175">Ist der Fehlerbericht, der vom auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f59ba-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-176"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-177">smallint</span><span class="sxs-lookup"><span data-stu-id="f59ba-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f59ba-178">Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f59ba-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-179"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-180">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="f59ba-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f59ba-181">Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="f59ba-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="f59ba-182">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f59ba-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-184">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f59ba-185">Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f59ba-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="f59ba-186">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f59ba-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59ba-187"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-188">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-188">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-189">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-190">Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.</span><span class="sxs-lookup"><span data-stu-id="f59ba-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59ba-191"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="f59ba-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f59ba-192">int</span><span class="sxs-lookup"><span data-stu-id="f59ba-192">int</span></span></p></td>
<td><p><span data-ttu-id="f59ba-193">Fremd</span><span class="sxs-lookup"><span data-stu-id="f59ba-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f59ba-194">Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f59ba-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

