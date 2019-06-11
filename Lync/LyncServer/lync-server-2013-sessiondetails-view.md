---
title: 'Lync Server 2013: SessionDetails-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="33f3b-102">SessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33f3b-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33f3b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="33f3b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="33f3b-104">In der SessionDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP-Anruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann.</span><span class="sxs-lookup"><span data-stu-id="33f3b-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="33f3b-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="33f3b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33f3b-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="33f3b-106">Column</span></span></th>
<th><span data-ttu-id="33f3b-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="33f3b-107">Data Type</span></span></th>
<th><span data-ttu-id="33f3b-108">Details</span><span class="sxs-lookup"><span data-stu-id="33f3b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="33f3b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="33f3b-111">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="33f3b-111">Time of session request.</span></span> <span data-ttu-id="33f3b-112">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33f3b-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="33f3b-113">Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-dialogs-table.md">Dialogfelder in der lync Server 2013</a> -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="33f3b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-115">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-115">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-116">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33f3b-116">ID number to identify the session.</span></span> <span data-ttu-id="33f3b-117">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33f3b-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="33f3b-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-119"><strong>Einladen</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-120">datetime</span><span class="sxs-lookup"><span data-stu-id="33f3b-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="33f3b-121">Uhrzeit der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="33f3b-121">Time of the first INVITE request.</span></span> <span data-ttu-id="33f3b-122">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33f3b-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="33f3b-123">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="33f3b-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="33f3b-124">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33f3b-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="33f3b-125">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="33f3b-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33f3b-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-128">Der URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-129"><strong>Touri</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33f3b-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-131">Der URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-134">Der Typ des URIs des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="33f3b-135">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-138">Der Typ des URIs des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="33f3b-139">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33f3b-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-142">Der Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="33f3b-143">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-144"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-146">Der Mandant des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="33f3b-147">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="33f3b-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="33f3b-150">Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-151"><strong>Endpunkt-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="33f3b-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="33f3b-153">Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-155">datetime</span><span class="sxs-lookup"><span data-stu-id="33f3b-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="33f3b-156">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f3b-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-158">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-158">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-159">Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-161">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-161">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-162">Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-165">Die Version des Clients, die von dem Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-167">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-167">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-168">Der Client, der von dem Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-168">Client used by the user who started the session.</span></span> <span data-ttu-id="33f3b-169">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="33f3b-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-172">Der Name der Kategorie des Clients, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-175">Die Version des Clients, die von dem Benutzer verwendet wird, der der Sitzung beigetreten ist</span><span class="sxs-lookup"><span data-stu-id="33f3b-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-176"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-177">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-177">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-178">Der Client, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="33f3b-179">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="33f3b-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-182">Der Name der Kategorie des Clients, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33f3b-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-185">Der URI des Zielbenutzers der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f3b-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33f3b-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-188">Der Typ des URIs des Zielbenutzers für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f3b-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="33f3b-189">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33f3b-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-192">Der URI des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="33f3b-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-195">Der Typ des URIs des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="33f3b-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="33f3b-196">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-199">Der Mandant des Benutzers, dessen Namen für die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="33f3b-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="33f3b-200">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33f3b-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-203">Der URI des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-206">Der Typ des URIs des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="33f3b-207">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-210">Der Mandant des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="33f3b-211">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-212"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="33f3b-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-214">SIP-Dialogfeld-ID.</span><span class="sxs-lookup"><span data-stu-id="33f3b-214">SIP dialog ID.</span></span> <span data-ttu-id="33f3b-215">Das Format lautet:</span><span class="sxs-lookup"><span data-stu-id="33f3b-215">The format is:</span></span></p>
<p><span data-ttu-id="33f3b-216">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="33f3b-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="33f3b-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="33f3b-219">GUID, die verwendet wird, um mehrere Sitzungen zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="33f3b-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-221">datetime</span><span class="sxs-lookup"><span data-stu-id="33f3b-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="33f3b-222">Uhrzeit des Dialogs, der durch die Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="33f3b-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="33f3b-223">Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33f3b-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="33f3b-224">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-226">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-226">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-227">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33f3b-227">ID number to identify the session.</span></span> <span data-ttu-id="33f3b-228">Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33f3b-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="33f3b-229">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33f3b-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="33f3b-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-232">SIP-Dialog-ID, die die Sitzung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="33f3b-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="33f3b-233">Das Format lautet:</span><span class="sxs-lookup"><span data-stu-id="33f3b-233">The format is:</span></span></p>
<p><span data-ttu-id="33f3b-234">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="33f3b-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-235"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-236">datetime</span><span class="sxs-lookup"><span data-stu-id="33f3b-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="33f3b-237">Zeitpunkt der Antwort auf die erste Einladungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="33f3b-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="33f3b-238">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33f3b-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="33f3b-239">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="33f3b-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-240"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-241">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-241">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-242">SIP-Antwortcode für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="33f3b-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="33f3b-243">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33f3b-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="33f3b-244">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="33f3b-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-245"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-246">int</span><span class="sxs-lookup"><span data-stu-id="33f3b-246">int</span></span></p></td>
<td><p><span data-ttu-id="33f3b-247">Von SIP-Headern erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="33f3b-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-250">Der Typ des Inhalts für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f3b-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-253">FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-256">Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="33f3b-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-259">Der FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-262">FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat</span><span class="sxs-lookup"><span data-stu-id="33f3b-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-264">bit</span><span class="sxs-lookup"><span data-stu-id="33f3b-264">bit</span></span></p></td>
<td><p><span data-ttu-id="33f3b-265">Gibt an, ob der Benutzer, der die Sitzung gestartet hat, sich über das interne Netzwerk angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-267">bit</span><span class="sxs-lookup"><span data-stu-id="33f3b-267">bit</span></span></p></td>
<td><p><span data-ttu-id="33f3b-268">Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, aus dem internen Netzwerk angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="33f3b-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33f3b-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-271">Anrufpriorität der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f3b-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-273">smallint</span><span class="sxs-lookup"><span data-stu-id="33f3b-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="33f3b-274">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="33f3b-275">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="33f3b-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="33f3b-276">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="33f3b-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-278">smallint</span><span class="sxs-lookup"><span data-stu-id="33f3b-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="33f3b-279">Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="33f3b-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="33f3b-280">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="33f3b-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="33f3b-281">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="33f3b-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33f3b-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-283">smallint</span><span class="sxs-lookup"><span data-stu-id="33f3b-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="33f3b-284">Gibt die anrufattribute an.</span><span class="sxs-lookup"><span data-stu-id="33f3b-284">Indicates the call attributes.</span></span> <span data-ttu-id="33f3b-285">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="33f3b-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="33f3b-286">0x01-wiederholte Sitzung</span><span class="sxs-lookup"><span data-stu-id="33f3b-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="33f3b-287">0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="33f3b-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33f3b-288"><strong>Standort</strong></span><span class="sxs-lookup"><span data-stu-id="33f3b-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="33f3b-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="33f3b-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="33f3b-290">Ort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="33f3b-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

