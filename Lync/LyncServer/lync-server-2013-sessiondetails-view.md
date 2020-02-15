---
title: 'Lync Server 2013: SessionDetails-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb7b664761aa8506b01e114366016b98637eb30e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="61f18-102">SessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61f18-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61f18-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="61f18-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="61f18-104">In der SessionDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um VoIP-VoIP-Telefonanrufe, Chatsitzungen mit zwei Teilnehmern oder andere Sitzungstypen handeln kann.</span><span class="sxs-lookup"><span data-stu-id="61f18-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="61f18-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="61f18-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61f18-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="61f18-106">Column</span></span></th>
<th><span data-ttu-id="61f18-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="61f18-107">Data Type</span></span></th>
<th><span data-ttu-id="61f18-108">Details</span><span class="sxs-lookup"><span data-stu-id="61f18-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61f18-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61f18-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f18-111">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="61f18-111">Time of session request.</span></span> <span data-ttu-id="61f18-112">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="61f18-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="61f18-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> Tabelle.</span><span class="sxs-lookup"><span data-stu-id="61f18-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-115">int</span><span class="sxs-lookup"><span data-stu-id="61f18-115">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-116">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f18-116">ID number to identify the session.</span></span> <span data-ttu-id="61f18-117">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="61f18-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="61f18-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-119"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-120">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61f18-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f18-p104">Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="61f18-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f18-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f18-128">URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-129"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f18-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f18-131">URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-134">Typ des URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="61f18-135">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-138">Typ des URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="61f18-139">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f18-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f18-142">Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="61f18-143">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-144"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-146">Mandant des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="61f18-147">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="61f18-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="61f18-150">Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-151"><strong>Toendpointo</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="61f18-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="61f18-153">Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-155">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61f18-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f18-156">Endzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f18-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-158">int</span><span class="sxs-lookup"><span data-stu-id="61f18-158">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-159">Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-161">int</span><span class="sxs-lookup"><span data-stu-id="61f18-161">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-162">Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-165">Version des Clients, die der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-167">int</span><span class="sxs-lookup"><span data-stu-id="61f18-167">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-168">Client, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-168">Client used by the user who started the session.</span></span> <span data-ttu-id="61f18-169">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="61f18-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61f18-172">Name der Kategorie des Clients, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-175">Version des Clients, die der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-176"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-177">int</span><span class="sxs-lookup"><span data-stu-id="61f18-177">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-178">Client, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="61f18-179">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="61f18-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61f18-182">Name der Kategorie des Clients, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f18-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f18-185">URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f18-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f18-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f18-188">Typ des URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f18-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="61f18-189">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f18-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f18-192">URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-195">Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="61f18-196">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-199">Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="61f18-200">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f18-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f18-203">URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-206">Typ des URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="61f18-207">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-210">Mandant des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="61f18-211">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-212"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="61f18-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="61f18-p116">SIP-Dialog-ID. Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="61f18-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="61f18-216">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="61f18-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="61f18-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="61f18-219">GUID zum Korrelieren mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="61f18-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-221">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61f18-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f18-222">Zeitpunkt des Dialogs, der durch die Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="61f18-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="61f18-223">Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="61f18-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="61f18-224">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-226">int</span><span class="sxs-lookup"><span data-stu-id="61f18-226">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-227">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f18-227">ID number to identify the session.</span></span> <span data-ttu-id="61f18-228">Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="61f18-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="61f18-229">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f18-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="61f18-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="61f18-p119">SIP-Dialog-ID, die durch die Sitzung ersetzt wird. Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="61f18-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="61f18-234">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="61f18-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-235"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-236">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61f18-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f18-p120">Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="61f18-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-241">int</span><span class="sxs-lookup"><span data-stu-id="61f18-241">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="61f18-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-245"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-246">int</span><span class="sxs-lookup"><span data-stu-id="61f18-246">int</span></span></p></td>
<td><p><span data-ttu-id="61f18-247">Diagnose-ID, die aus SIP-Headern erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="61f18-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-250">Typ des Inhalts für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f18-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-251"><strong>Frontend</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-253">Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-256">Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-259">Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61f18-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-262">Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61f18-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-264">Bit</span><span class="sxs-lookup"><span data-stu-id="61f18-264">bit</span></span></p></td>
<td><p><span data-ttu-id="61f18-265">Gibt an, ob der Benutzer, der die Sitzung gestartet hat, über das interne Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="61f18-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-267">Bit</span><span class="sxs-lookup"><span data-stu-id="61f18-267">bit</span></span></p></td>
<td><p><span data-ttu-id="61f18-268">Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, über das interne Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="61f18-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f18-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f18-271">Anrufpriorität der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f18-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-273">smallint</span><span class="sxs-lookup"><span data-stu-id="61f18-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f18-p122">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="61f18-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="61f18-276">0x01 - Mit dem Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="61f18-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-278">smallint</span><span class="sxs-lookup"><span data-stu-id="61f18-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f18-p123">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="61f18-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="61f18-281">0x01 - Mit dem Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="61f18-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f18-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-283">smallint</span><span class="sxs-lookup"><span data-stu-id="61f18-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f18-p124">Gibt die Anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="61f18-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="61f18-286">0x01 - Sitzung mit Wiederholungsversuch</span><span class="sxs-lookup"><span data-stu-id="61f18-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="61f18-287">0x02 - Ein vom Agent im Namen einer Reaktionsgruppe getätigter Anruf</span><span class="sxs-lookup"><span data-stu-id="61f18-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f18-288"><strong>Standort</strong></span><span class="sxs-lookup"><span data-stu-id="61f18-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="61f18-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="61f18-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="61f18-290">Standort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="61f18-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

