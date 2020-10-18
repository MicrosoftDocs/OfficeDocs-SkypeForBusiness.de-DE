---
title: 'Lync Server 2013: SessionDetails-Ansicht'
description: 'Lync Server 2013: SessionDetails-Ansicht.'
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573241"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="a436c-103">SessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a436c-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a436c-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a436c-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a436c-105">In der SessionDetails-Ansicht werden Informationen über Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP Telefonanruf, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann.</span><span class="sxs-lookup"><span data-stu-id="a436c-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="a436c-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a436c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a436c-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="a436c-107">Column</span></span></th>
<th><span data-ttu-id="a436c-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a436c-108">Data Type</span></span></th>
<th><span data-ttu-id="a436c-109">Details</span><span class="sxs-lookup"><span data-stu-id="a436c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a436c-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a436c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a436c-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="a436c-112">Time of session request.</span></span> <span data-ttu-id="a436c-113">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="a436c-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a436c-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a436c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-116">int</span><span class="sxs-lookup"><span data-stu-id="a436c-116">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a436c-117">ID number to identify the session.</span></span> <span data-ttu-id="a436c-118">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a436c-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a436c-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-120"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a436c-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="a436c-p104">Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a436c-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a436c-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a436c-129">URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-130"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a436c-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a436c-132">URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-135">Typ des URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="a436c-136">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-139">Typ des URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="a436c-140">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a436c-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a436c-143">Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="a436c-144">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-145"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-147">Mandant des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="a436c-148">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-150">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a436c-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a436c-151">Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-152"><strong>Toendpointo</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-153">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a436c-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a436c-154">Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-156">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a436c-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="a436c-157">Endzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a436c-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-159">int</span><span class="sxs-lookup"><span data-stu-id="a436c-159">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-160">Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-162">int</span><span class="sxs-lookup"><span data-stu-id="a436c-162">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-163">Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-166">Version des Clients, die der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-168">int</span><span class="sxs-lookup"><span data-stu-id="a436c-168">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-169">Client, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-169">Client used by the user who started the session.</span></span> <span data-ttu-id="a436c-170">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a436c-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a436c-173">Name der Kategorie des Clients, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-176">Version des Clients, die der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-177"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-178">int</span><span class="sxs-lookup"><span data-stu-id="a436c-178">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-179">Client, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="a436c-180">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a436c-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a436c-183">Name der Kategorie des Clients, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a436c-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a436c-186">URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a436c-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a436c-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a436c-189">Typ des URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a436c-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="a436c-190">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a436c-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a436c-193">URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-196">Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="a436c-197">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-200">Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="a436c-201">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a436c-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a436c-204">URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-207">Typ des URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="a436c-208">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-211">Mandant des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="a436c-212">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-213"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-214">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="a436c-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a436c-p116">SIP-Dialog-ID. Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a436c-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="a436c-217">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a436c-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-218"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-219">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a436c-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a436c-220">GUID zum Korrelieren mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="a436c-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-222">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a436c-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="a436c-223">Zeitpunkt des Dialogs, der durch die Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="a436c-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="a436c-224">Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a436c-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="a436c-225">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-227">int</span><span class="sxs-lookup"><span data-stu-id="a436c-227">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-228">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a436c-228">ID number to identify the session.</span></span> <span data-ttu-id="a436c-229">Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a436c-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="a436c-230">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a436c-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-232">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="a436c-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a436c-p119">SIP-Dialog-ID, die durch die Sitzung ersetzt wird. Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a436c-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="a436c-235">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a436c-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-236"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-237">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a436c-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="a436c-p120">Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a436c-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-242">int</span><span class="sxs-lookup"><span data-stu-id="a436c-242">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a436c-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-246"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-247">int</span><span class="sxs-lookup"><span data-stu-id="a436c-247">int</span></span></p></td>
<td><p><span data-ttu-id="a436c-248">Diagnose-ID, die aus SIP-Headern erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="a436c-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-251">Typ des Inhalts für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a436c-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-254">Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-255"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-257">Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-260">Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a436c-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-263">Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a436c-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-265">Bit</span><span class="sxs-lookup"><span data-stu-id="a436c-265">bit</span></span></p></td>
<td><p><span data-ttu-id="a436c-266">Gibt an, ob der Benutzer, der die Sitzung gestartet hat, über das interne Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="a436c-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-268">Bit</span><span class="sxs-lookup"><span data-stu-id="a436c-268">bit</span></span></p></td>
<td><p><span data-ttu-id="a436c-269">Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, über das interne Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="a436c-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a436c-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a436c-272">Anrufpriorität der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a436c-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-274">smallint</span><span class="sxs-lookup"><span data-stu-id="a436c-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="a436c-p122">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="a436c-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a436c-277">0x01 - Mit dem Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="a436c-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-279">smallint</span><span class="sxs-lookup"><span data-stu-id="a436c-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="a436c-p123">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="a436c-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a436c-282">0x01 - Mit dem Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="a436c-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a436c-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-284">smallint</span><span class="sxs-lookup"><span data-stu-id="a436c-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="a436c-p124">Gibt die Anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="a436c-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a436c-287">0x01 - Sitzung mit Wiederholungsversuch</span><span class="sxs-lookup"><span data-stu-id="a436c-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="a436c-288">0x02 - Ein vom Agent im Namen einer Reaktionsgruppe getätigter Anruf</span><span class="sxs-lookup"><span data-stu-id="a436c-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a436c-289"><strong>Ort</strong></span><span class="sxs-lookup"><span data-stu-id="a436c-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="a436c-290">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="a436c-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="a436c-291">Standort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="a436c-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

