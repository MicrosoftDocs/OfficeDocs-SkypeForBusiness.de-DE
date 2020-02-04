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
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="a2c65-102">SessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2c65-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2c65-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a2c65-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a2c65-104">In der SessionDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP-Anruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann.</span><span class="sxs-lookup"><span data-stu-id="a2c65-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="a2c65-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a2c65-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2c65-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="a2c65-106">Column</span></span></th>
<th><span data-ttu-id="a2c65-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a2c65-107">Data Type</span></span></th>
<th><span data-ttu-id="a2c65-108">Details</span><span class="sxs-lookup"><span data-stu-id="a2c65-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a2c65-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2c65-111">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="a2c65-111">Time of session request.</span></span> <span data-ttu-id="a2c65-112">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a2c65-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a2c65-113">Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-dialogs-table.md">Dialogfelder in der lync Server 2013</a> -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a2c65-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-115">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-115">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-116">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a2c65-116">ID number to identify the session.</span></span> <span data-ttu-id="a2c65-117">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a2c65-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a2c65-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-119"><strong>Einladen</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-120">datetime</span><span class="sxs-lookup"><span data-stu-id="a2c65-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2c65-121">Uhrzeit der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a2c65-121">Time of the first INVITE request.</span></span> <span data-ttu-id="a2c65-122">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a2c65-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a2c65-123">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="a2c65-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="a2c65-124">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a2c65-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a2c65-125">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="a2c65-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a2c65-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-128">Der URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-129"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a2c65-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-131">Der URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-134">Der Typ des URIs des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="a2c65-135">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-138">Der Typ des URIs des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="a2c65-139">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a2c65-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-142">Der Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="a2c65-143">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-144"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-146">Der Mandant des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="a2c65-147">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a2c65-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a2c65-150">Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-151"><strong>Endpunkt-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a2c65-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a2c65-153">Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-155">datetime</span><span class="sxs-lookup"><span data-stu-id="a2c65-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2c65-156">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a2c65-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-158">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-158">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-159">Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-161">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-161">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-162">Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-165">Die Version des Clients, die von dem Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-167">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-167">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-168">Der Client, der von dem Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-168">Client used by the user who started the session.</span></span> <span data-ttu-id="a2c65-169">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a2c65-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-172">Der Name der Kategorie des Clients, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-175">Die Version des Clients, die von dem Benutzer verwendet wird, der der Sitzung beigetreten ist</span><span class="sxs-lookup"><span data-stu-id="a2c65-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-176"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-177">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-177">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-178">Der Client, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="a2c65-179">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a2c65-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-182">Der Name der Kategorie des Clients, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a2c65-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-185">Der URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a2c65-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a2c65-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-188">Der Typ des URIs des Zielbenutzers für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a2c65-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="a2c65-189">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a2c65-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-192">Der URI des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a2c65-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-195">Der Typ des URIs des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a2c65-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="a2c65-196">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-199">Der Mandant des Benutzers, dessen Namen für die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a2c65-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="a2c65-200">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a2c65-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-203">Der URI des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-206">Der Typ des URIs des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="a2c65-207">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-210">Der Mandant des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="a2c65-211">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-212"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="a2c65-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-214">SIP-Dialogfeld-ID.</span><span class="sxs-lookup"><span data-stu-id="a2c65-214">SIP dialog ID.</span></span> <span data-ttu-id="a2c65-215">Das Format lautet:</span><span class="sxs-lookup"><span data-stu-id="a2c65-215">The format is:</span></span></p>
<p><span data-ttu-id="a2c65-216">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a2c65-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a2c65-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a2c65-219">GUID, die verwendet wird, um mehrere Sitzungen zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="a2c65-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-221">datetime</span><span class="sxs-lookup"><span data-stu-id="a2c65-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2c65-222">Uhrzeit des Dialogs, der durch die Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="a2c65-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="a2c65-223">Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a2c65-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="a2c65-224">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-226">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-226">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-227">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a2c65-227">ID number to identify the session.</span></span> <span data-ttu-id="a2c65-228">Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a2c65-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="a2c65-229">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2c65-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="a2c65-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-232">SIP-Dialog-ID, die die Sitzung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a2c65-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="a2c65-233">Das Format lautet:</span><span class="sxs-lookup"><span data-stu-id="a2c65-233">The format is:</span></span></p>
<p><span data-ttu-id="a2c65-234">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a2c65-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-235"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-236">datetime</span><span class="sxs-lookup"><span data-stu-id="a2c65-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2c65-237">Zeitpunkt der Antwort auf die erste Einladungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="a2c65-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="a2c65-238">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a2c65-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a2c65-239">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="a2c65-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-240"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-241">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-241">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-242">SIP-Antwortcode für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="a2c65-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="a2c65-243">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a2c65-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a2c65-244">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="a2c65-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-245"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-246">int</span><span class="sxs-lookup"><span data-stu-id="a2c65-246">int</span></span></p></td>
<td><p><span data-ttu-id="a2c65-247">Von SIP-Headern erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="a2c65-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-250">Der Typ des Inhalts für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a2c65-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-253">FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-256">Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="a2c65-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-259">Der FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-262">FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat</span><span class="sxs-lookup"><span data-stu-id="a2c65-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-264">bit</span><span class="sxs-lookup"><span data-stu-id="a2c65-264">bit</span></span></p></td>
<td><p><span data-ttu-id="a2c65-265">Gibt an, ob der Benutzer, der die Sitzung gestartet hat, sich über das interne Netzwerk angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-267">bit</span><span class="sxs-lookup"><span data-stu-id="a2c65-267">bit</span></span></p></td>
<td><p><span data-ttu-id="a2c65-268">Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, aus dem internen Netzwerk angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="a2c65-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2c65-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-271">Anrufpriorität der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a2c65-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-273">smallint</span><span class="sxs-lookup"><span data-stu-id="a2c65-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="a2c65-274">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="a2c65-275">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="a2c65-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a2c65-276">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="a2c65-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-278">smallint</span><span class="sxs-lookup"><span data-stu-id="a2c65-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="a2c65-279">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="a2c65-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="a2c65-280">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="a2c65-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a2c65-281">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="a2c65-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c65-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-283">smallint</span><span class="sxs-lookup"><span data-stu-id="a2c65-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="a2c65-284">Gibt die anrufattribute an.</span><span class="sxs-lookup"><span data-stu-id="a2c65-284">Indicates the call attributes.</span></span> <span data-ttu-id="a2c65-285">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="a2c65-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a2c65-286">0x01-wiederholte Sitzung</span><span class="sxs-lookup"><span data-stu-id="a2c65-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="a2c65-287">0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="a2c65-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c65-288"><strong>Standort</strong></span><span class="sxs-lookup"><span data-stu-id="a2c65-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="a2c65-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="a2c65-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="a2c65-290">Ort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="a2c65-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

