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
ms.openlocfilehash: 8baf67ce72103ef0dda64a9b0b43a8f6dd6402f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510062"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="098d1-102">SessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="098d1-102">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="098d1-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="098d1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="098d1-104">In der SessionDetails-Ansicht werden Informationen über Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP Telefonanruf, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann.</span><span class="sxs-lookup"><span data-stu-id="098d1-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="098d1-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="098d1-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="098d1-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="098d1-106">Column</span></span></th>
<th><span data-ttu-id="098d1-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="098d1-107">Data Type</span></span></th>
<th><span data-ttu-id="098d1-108">Details</span><span class="sxs-lookup"><span data-stu-id="098d1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="098d1-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="098d1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="098d1-111">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="098d1-111">Time of session request.</span></span> <span data-ttu-id="098d1-112">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="098d1-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="098d1-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> Tabelle.</span><span class="sxs-lookup"><span data-stu-id="098d1-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-115">int</span><span class="sxs-lookup"><span data-stu-id="098d1-115">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-116">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="098d1-116">ID number to identify the session.</span></span> <span data-ttu-id="098d1-117">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="098d1-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="098d1-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-119"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-120">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="098d1-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="098d1-p104">Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="098d1-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="098d1-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="098d1-128">URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-129"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="098d1-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="098d1-131">URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-134">Typ des URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="098d1-135">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-138">Typ des URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="098d1-139">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="098d1-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="098d1-142">Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="098d1-143">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-144"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-146">Mandant des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="098d1-147">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="098d1-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="098d1-150">Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-151"><strong>Toendpointo</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="098d1-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="098d1-153">Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-155">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="098d1-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="098d1-156">Endzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="098d1-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-158">int</span><span class="sxs-lookup"><span data-stu-id="098d1-158">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-159">Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-161">int</span><span class="sxs-lookup"><span data-stu-id="098d1-161">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-162">Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-165">Version des Clients, die der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-167">int</span><span class="sxs-lookup"><span data-stu-id="098d1-167">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-168">Client, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-168">Client used by the user who started the session.</span></span> <span data-ttu-id="098d1-169">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="098d1-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="098d1-172">Name der Kategorie des Clients, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-175">Version des Clients, die der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-176"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-177">int</span><span class="sxs-lookup"><span data-stu-id="098d1-177">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-178">Client, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="098d1-179">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="098d1-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="098d1-182">Name der Kategorie des Clients, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="098d1-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="098d1-185">URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="098d1-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="098d1-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="098d1-188">Typ des URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="098d1-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="098d1-189">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="098d1-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="098d1-192">URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-195">Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="098d1-196">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-199">Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="098d1-200">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="098d1-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="098d1-203">URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-206">Typ des URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="098d1-207">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-210">Mandant des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="098d1-211">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-212"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="098d1-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="098d1-p116">SIP-Dialog-ID. Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="098d1-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="098d1-216">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="098d1-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="098d1-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="098d1-219">GUID zum Korrelieren mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="098d1-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-221">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="098d1-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="098d1-222">Zeitpunkt des Dialogs, der durch die Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="098d1-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="098d1-223">Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="098d1-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="098d1-224">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-226">int</span><span class="sxs-lookup"><span data-stu-id="098d1-226">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-227">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="098d1-227">ID number to identify the session.</span></span> <span data-ttu-id="098d1-228">Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="098d1-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="098d1-229">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="098d1-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="098d1-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="098d1-p119">SIP-Dialog-ID, die durch die Sitzung ersetzt wird. Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="098d1-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="098d1-234">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="098d1-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-235"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-236">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="098d1-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="098d1-p120">Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="098d1-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-241">int</span><span class="sxs-lookup"><span data-stu-id="098d1-241">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="098d1-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-245"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-246">int</span><span class="sxs-lookup"><span data-stu-id="098d1-246">int</span></span></p></td>
<td><p><span data-ttu-id="098d1-247">Diagnose-ID, die aus SIP-Headern erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="098d1-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-250">Typ des Inhalts für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="098d1-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-253">Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-256">Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-259">Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="098d1-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-262">Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="098d1-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-264">Bit</span><span class="sxs-lookup"><span data-stu-id="098d1-264">bit</span></span></p></td>
<td><p><span data-ttu-id="098d1-265">Gibt an, ob der Benutzer, der die Sitzung gestartet hat, über das interne Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="098d1-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-267">Bit</span><span class="sxs-lookup"><span data-stu-id="098d1-267">bit</span></span></p></td>
<td><p><span data-ttu-id="098d1-268">Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, über das interne Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="098d1-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="098d1-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="098d1-271">Anrufpriorität der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="098d1-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-273">smallint</span><span class="sxs-lookup"><span data-stu-id="098d1-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="098d1-p122">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="098d1-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="098d1-276">0x01 - Mit dem Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="098d1-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-278">smallint</span><span class="sxs-lookup"><span data-stu-id="098d1-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="098d1-p123">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="098d1-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="098d1-281">0x01 - Mit dem Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="098d1-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098d1-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-283">smallint</span><span class="sxs-lookup"><span data-stu-id="098d1-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="098d1-p124">Gibt die Anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="098d1-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="098d1-286">0x01 - Sitzung mit Wiederholungsversuch</span><span class="sxs-lookup"><span data-stu-id="098d1-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="098d1-287">0x02 - Ein vom Agent im Namen einer Reaktionsgruppe getätigter Anruf</span><span class="sxs-lookup"><span data-stu-id="098d1-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098d1-288"><strong>Ort</strong></span><span class="sxs-lookup"><span data-stu-id="098d1-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="098d1-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="098d1-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="098d1-290">Standort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="098d1-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

