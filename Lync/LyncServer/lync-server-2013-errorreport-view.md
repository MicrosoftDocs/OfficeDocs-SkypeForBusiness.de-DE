---
title: 'Lync Server 2013: errorreport-Ansicht'
description: 'Lync Server 2013: errorreport-Ansicht.'
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
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572041"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="1b4c5-103">ErrorReport-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b4c5-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b4c5-104">_**Letztes Änderungsstand des Themas:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="1b4c5-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="1b4c5-105">In der errorreport-Ansicht werden Informationen zu gemeldeten Fehlern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="1b4c5-106">Bei jedem Datensatz handelt es sich um ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-106">Each record is one error occurrence.</span></span> <span data-ttu-id="1b4c5-107">Die Fehler werden entweder von dem auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="1b4c5-108">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b4c5-109">Spalte</span><span class="sxs-lookup"><span data-stu-id="1b4c5-109">Column</span></span></th>
<th><span data-ttu-id="1b4c5-110">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1b4c5-110">Data Type</span></span></th>
<th><span data-ttu-id="1b4c5-111">Details</span><span class="sxs-lookup"><span data-stu-id="1b4c5-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-112"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1b4c5-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-p102">Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-117">int</span><span class="sxs-lookup"><span data-stu-id="1b4c5-117">int</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-p103">ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-121">int</span><span class="sxs-lookup"><span data-stu-id="1b4c5-121">int</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-122">Diagnose-ID für den Fehlerbericht.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-125">URI des Benutzers, von dem der Fehler stammt.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-128">URI-Typ des Benutzers, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="1b4c5-129">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-132">Mandant des Benutzers, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="1b4c5-133">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-134"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-136">URI des Benutzers, der das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-139">URI-Typ des Benutzers, der das Ziel des Fehlerberichts ist.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-139">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="1b4c5-140">Weitere Informationen finden Sie in der UriTypes Table.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-140">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-141"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-143">Mandant des Benutzers, der den Fehlerbericht abzielt.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="1b4c5-144">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-145"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-147">URI der Konferenz, die das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-150">URI-Typ der Konferenz, die das Ziel des Fehlerberichts war.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="1b4c5-151">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-152"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-153">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1b4c5-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-154">Zeitpunkt der Sitzungsanforderung, von der der Fehlerbericht stammt.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="1b4c5-155">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="1b4c5-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1b4c5-156">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-158">int</span><span class="sxs-lookup"><span data-stu-id="1b4c5-158">int</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-159">ID-Nummer zum Identifizieren der Sitzungsanforderung, von der der Fehlerbericht stammt.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="1b4c5-160">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="1b4c5-161">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-162"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-163">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-164">SIP-Dialogfeld-ID der Sitzung mit Ursprung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-164">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="1b4c5-165">Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1b4c5-165">The format is:</span></span></p>
<p><span data-ttu-id="1b4c5-166">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="1b4c5-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="1b4c5-167">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="1b4c5-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="1b4c5-168">Umwandlung (Umwandlung (extern-als varbinary (max)) als varchar (max))</span><span class="sxs-lookup"><span data-stu-id="1b4c5-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-171">Version des Clients, die von dem Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-173">int</span><span class="sxs-lookup"><span data-stu-id="1b4c5-173">int</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-174">Client, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="1b4c5-175">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-178">Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-181">Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="1b4c5-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-182"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-184">Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="1b4c5-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-186">int</span><span class="sxs-lookup"><span data-stu-id="1b4c5-186">int</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-187">SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-189">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-190">Der Typ der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-192">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-193">Der Inhaltstyp der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-196">Der Sitzungstyp.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-196">Type of session.</span></span> <span data-ttu-id="1b4c5-197">Weitere Informationen finden Sie <a href="lync-server-2013-calltype-table.md">in der CallType-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b4c5-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-198"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-199">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1b4c5-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-200">Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-201"><strong>Rüstzeit</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-202">int</span><span class="sxs-lookup"><span data-stu-id="1b4c5-202">int</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-203">Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-205">Bit</span><span class="sxs-lookup"><span data-stu-id="1b4c5-205">bit</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-206">Gibt an, ob der Fehlerbericht vom auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-207"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-208">smallint</span><span class="sxs-lookup"><span data-stu-id="1b4c5-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-209">Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-211">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1b4c5-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-212">Zusätzliche Informationen zu dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b4c5-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="1b4c5-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-215">Vollqualifizierter Domänenname des Front-End-Servers, der den Bericht übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4c5-216"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1b4c5-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4c5-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="1b4c5-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="1b4c5-218">Vollqualifizierter Domänenname des Pools mit dem Front-End-Server, der den Bericht übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

