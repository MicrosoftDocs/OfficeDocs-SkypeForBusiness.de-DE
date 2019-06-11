---
title: 'Lync Server 2013: errorreport-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="401f9-102">ErrorReport-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="401f9-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="401f9-103">_**Letztes Änderungsdatum des Themas:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="401f9-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="401f9-104">In der errorreport-Ansicht werden Informationen zu den gemeldeten Fehlern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="401f9-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="401f9-105">Bei jedem Datensatz handelt es sich um ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="401f9-105">Each record is one error occurrence.</span></span> <span data-ttu-id="401f9-106">Die Fehler werden entweder vom CDR-Agent, der auf dem Front-End-Server ausgeführt wird, erfasst oder vom Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="401f9-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="401f9-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="401f9-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="401f9-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="401f9-108">Column</span></span></th>
<th><span data-ttu-id="401f9-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="401f9-109">Data Type</span></span></th>
<th><span data-ttu-id="401f9-110">Details</span><span class="sxs-lookup"><span data-stu-id="401f9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="401f9-111"><strong>Fehlerzeit</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-112">datetime</span><span class="sxs-lookup"><span data-stu-id="401f9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="401f9-113">Zeitpunkt des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="401f9-113">Time of error occurred.</span></span> <span data-ttu-id="401f9-114">Wird in Verbindung mit ErrorReportSeq verwendet, um einen Fehler eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="401f9-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-116">int</span><span class="sxs-lookup"><span data-stu-id="401f9-116">int</span></span></p></td>
<td><p><span data-ttu-id="401f9-117">Die ID-Nummer, um den Fehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="401f9-117">ID number to identify the error.</span></span> <span data-ttu-id="401f9-118">Wird in Verbindung mit Fehlerzeit verwendet, um einen Fehler eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="401f9-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-120">int</span><span class="sxs-lookup"><span data-stu-id="401f9-120">int</span></span></p></td>
<td><p><span data-ttu-id="401f9-121">Diagnose-ID für den Fehlerbericht.</span><span class="sxs-lookup"><span data-stu-id="401f9-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="401f9-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="401f9-124">Der URI des Benutzers, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-127">Der Typ des URIs des Benutzers, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="401f9-128">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-131">Der Mandant des Benutzers, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="401f9-132">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-133"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="401f9-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="401f9-135">Der URI des Benutzers, der das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="401f9-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-138">Der Typ des URIs des Benutzers, der auf den Fehlerbericht ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="401f9-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="401f9-139">Weitere Informationen finden Sie in der UriTypes-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="401f9-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-140"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-142">Der Mandant des Benutzers, der auf den Fehlerbericht abzielt.</span><span class="sxs-lookup"><span data-stu-id="401f9-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="401f9-143">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="401f9-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="401f9-146">Der URI der Konferenz, die das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="401f9-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-149">Der URI-Typ der Konferenz, die das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="401f9-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="401f9-150">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-151"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-152">datetime</span><span class="sxs-lookup"><span data-stu-id="401f9-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="401f9-153">Die Uhrzeit der Sitzungsanforderung, von der der Fehlerbericht stammt.</span><span class="sxs-lookup"><span data-stu-id="401f9-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="401f9-154">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="401f9-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="401f9-155">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-157">int</span><span class="sxs-lookup"><span data-stu-id="401f9-157">int</span></span></p></td>
<td><p><span data-ttu-id="401f9-158">Die ID-Nummer, mit der die Sitzungsanforderung identifiziert wird, von der der Fehlerbericht stammt.</span><span class="sxs-lookup"><span data-stu-id="401f9-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="401f9-159">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="401f9-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="401f9-160">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-161"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="401f9-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="401f9-163">SIP-Dialogfeld-ID der Sitzung, die den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="401f9-164">Das Format lautet:</span><span class="sxs-lookup"><span data-stu-id="401f9-164">The format is:</span></span></p>
<p><span data-ttu-id="401f9-165">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="401f9-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="401f9-166">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="401f9-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="401f9-167">Umwandlung (Umwandlung (extern-als varbinary (max)) als varchar (max))</span><span class="sxs-lookup"><span data-stu-id="401f9-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-170">Die Version des Clients, die von dem Benutzer verwendet wird, der den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-171"><strong>Clienttyp</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-172">int</span><span class="sxs-lookup"><span data-stu-id="401f9-172">int</span></span></p></td>
<td><p><span data-ttu-id="401f9-173">Der Client, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="401f9-174">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="401f9-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="401f9-177">Der Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-178"><strong>Quelle</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-180">Name des Servers, der den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="401f9-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-181"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-183">Der Name der Anwendung, die den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="401f9-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-184"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-185">int</span><span class="sxs-lookup"><span data-stu-id="401f9-185">int</span></span></p></td>
<td><p><span data-ttu-id="401f9-186">SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.</span><span class="sxs-lookup"><span data-stu-id="401f9-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="401f9-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="401f9-189">Der Typ der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="401f9-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="401f9-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="401f9-192">Inhaltstyp der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="401f9-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="401f9-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="401f9-195">Der Sitzungstyp.</span><span class="sxs-lookup"><span data-stu-id="401f9-195">Type of session.</span></span> <span data-ttu-id="401f9-196">Weitere Informationen finden Sie in der Tabelle "CallType" <a href="lync-server-2013-calltype-table.md">in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="401f9-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-197"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-198">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="401f9-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="401f9-199">Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="401f9-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-200"><strong>Rüstzeit</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-201">int</span><span class="sxs-lookup"><span data-stu-id="401f9-201">int</span></span></p></td>
<td><p><span data-ttu-id="401f9-202">Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="401f9-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-204">bit</span><span class="sxs-lookup"><span data-stu-id="401f9-204">bit</span></span></p></td>
<td><p><span data-ttu-id="401f9-205">Gibt an, ob der Fehlerbericht vom auf dem Front-End-Server ausgeführten CDR-Agent erfasst oder vom Client gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="401f9-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-206"><strong>Kennzeichnen</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-207">smallint</span><span class="sxs-lookup"><span data-stu-id="401f9-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="401f9-208">Für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="401f9-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="401f9-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="401f9-211">Weitere Informationen zum Fehler.</span><span class="sxs-lookup"><span data-stu-id="401f9-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401f9-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="401f9-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="401f9-214">Vollständig qualifizierter Domänenname des Front-End-Servers, der den Bericht übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401f9-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="401f9-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="401f9-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="401f9-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="401f9-217">Vollständig qualifizierter Domänenname des Pools, der den Front-End-Server enthält, der den Bericht übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="401f9-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

