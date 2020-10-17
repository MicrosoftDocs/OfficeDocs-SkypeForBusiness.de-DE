---
title: 'Lync Server 2013: errorreport-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8792154c88c74049a785ddfb9ebbca55a52bc26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514452"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="f74d6-102">ErrorReport-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f74d6-102">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f74d6-103">_**Letztes Änderungsstand des Themas:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="f74d6-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="f74d6-104">In der errorreport-Ansicht werden Informationen zu gemeldeten Fehlern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f74d6-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="f74d6-105">Bei jedem Datensatz handelt es sich um ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="f74d6-105">Each record is one error occurrence.</span></span> <span data-ttu-id="f74d6-106">Die Fehler werden entweder von dem auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="f74d6-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="f74d6-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f74d6-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f74d6-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="f74d6-108">Column</span></span></th>
<th><span data-ttu-id="f74d6-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f74d6-109">Data Type</span></span></th>
<th><span data-ttu-id="f74d6-110">Details</span><span class="sxs-lookup"><span data-stu-id="f74d6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-111"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f74d6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f74d6-p102">Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f74d6-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-116">int</span><span class="sxs-lookup"><span data-stu-id="f74d6-116">int</span></span></p></td>
<td><p><span data-ttu-id="f74d6-p103">ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f74d6-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-120">int</span><span class="sxs-lookup"><span data-stu-id="f74d6-120">int</span></span></p></td>
<td><p><span data-ttu-id="f74d6-121">Diagnose-ID für den Fehlerbericht.</span><span class="sxs-lookup"><span data-stu-id="f74d6-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f74d6-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-124">URI des Benutzers, von dem der Fehler stammt.</span><span class="sxs-lookup"><span data-stu-id="f74d6-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-127">URI-Typ des Benutzers, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f74d6-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="f74d6-128">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-131">Mandant des Benutzers, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f74d6-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="f74d6-132">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-133"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f74d6-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-135">URI des Benutzers, der das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="f74d6-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-138">URI-Typ des Benutzers, der das Ziel des Fehlerberichts ist.</span><span class="sxs-lookup"><span data-stu-id="f74d6-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="f74d6-139">Weitere Informationen finden Sie in der UriTypes Table.</span><span class="sxs-lookup"><span data-stu-id="f74d6-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-140"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-142">Mandant des Benutzers, der den Fehlerbericht abzielt.</span><span class="sxs-lookup"><span data-stu-id="f74d6-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="f74d6-143">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f74d6-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-146">URI der Konferenz, die das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="f74d6-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-149">URI-Typ der Konferenz, die das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="f74d6-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="f74d6-150">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-151"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-152">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f74d6-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="f74d6-153">Zeitpunkt der Sitzungsanforderung, von der der Fehlerbericht stammt.</span><span class="sxs-lookup"><span data-stu-id="f74d6-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="f74d6-154">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="f74d6-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f74d6-155">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-157">int</span><span class="sxs-lookup"><span data-stu-id="f74d6-157">int</span></span></p></td>
<td><p><span data-ttu-id="f74d6-158">ID-Nummer zum Identifizieren der Sitzungsanforderung, von der der Fehlerbericht stammt.</span><span class="sxs-lookup"><span data-stu-id="f74d6-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="f74d6-159">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f74d6-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f74d6-160">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-161"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="f74d6-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-163">SIP-Dialogfeld-ID der Sitzung mit Ursprung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="f74d6-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="f74d6-164">Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f74d6-164">The format is:</span></span></p>
<p><span data-ttu-id="f74d6-165">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="f74d6-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="f74d6-166">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="f74d6-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="f74d6-167">Umwandlung (Umwandlung (extern-als varbinary (max)) als varchar (max))</span><span class="sxs-lookup"><span data-stu-id="f74d6-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-170">Version des Clients, die von dem Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f74d6-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-172">int</span><span class="sxs-lookup"><span data-stu-id="f74d6-172">int</span></span></p></td>
<td><p><span data-ttu-id="f74d6-173">Client, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f74d6-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="f74d6-174">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f74d6-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-177">Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f74d6-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-180">Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="f74d6-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-181"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-183">Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="f74d6-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-185">int</span><span class="sxs-lookup"><span data-stu-id="f74d6-185">int</span></span></p></td>
<td><p><span data-ttu-id="f74d6-186">SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.</span><span class="sxs-lookup"><span data-stu-id="f74d6-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="f74d6-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-189">Der Typ der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f74d6-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="f74d6-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-192">Der Inhaltstyp der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f74d6-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f74d6-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-195">Der Sitzungstyp.</span><span class="sxs-lookup"><span data-stu-id="f74d6-195">Type of session.</span></span> <span data-ttu-id="f74d6-196">Weitere Informationen finden Sie <a href="lync-server-2013-calltype-table.md">in der CallType-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f74d6-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-197"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-198">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f74d6-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f74d6-199">Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="f74d6-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-200"><strong>Rüstzeit</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-201">int</span><span class="sxs-lookup"><span data-stu-id="f74d6-201">int</span></span></p></td>
<td><p><span data-ttu-id="f74d6-202">Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f74d6-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-204">Bit</span><span class="sxs-lookup"><span data-stu-id="f74d6-204">bit</span></span></p></td>
<td><p><span data-ttu-id="f74d6-205">Gibt an, ob der Fehlerbericht vom auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f74d6-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-206"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-207">smallint</span><span class="sxs-lookup"><span data-stu-id="f74d6-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="f74d6-208">Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f74d6-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="f74d6-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f74d6-211">Zusätzliche Informationen zu dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="f74d6-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f74d6-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="f74d6-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="f74d6-214">Vollqualifizierter Domänenname des Front-End-Servers, der den Bericht übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="f74d6-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f74d6-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f74d6-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f74d6-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="f74d6-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="f74d6-217">Vollqualifizierter Domänenname des Pools mit dem Front-End-Server, der den Bericht übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="f74d6-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

