---
title: 'Lync Server 2013: ConferenceSessionDetails-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="e860d-102">ConferenceSessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e860d-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e860d-103">_**Letztes Änderungsdatum des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e860d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e860d-104">In der ConferenceSessionDetails-Ansicht werden Informationen zu mehrteiligen Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e860d-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="e860d-105">Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann.</span><span class="sxs-lookup"><span data-stu-id="e860d-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="e860d-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e860d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e860d-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="e860d-107">Column</span></span></th>
<th><span data-ttu-id="e860d-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e860d-108">Data Type</span></span></th>
<th><span data-ttu-id="e860d-109">Details</span><span class="sxs-lookup"><span data-stu-id="e860d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e860d-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e860d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e860d-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e860d-112">Time of session request.</span></span> <span data-ttu-id="e860d-113">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e860d-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e860d-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-116">int</span><span class="sxs-lookup"><span data-stu-id="e860d-116">int</span></span></p></td>
<td><p><span data-ttu-id="e860d-117">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e860d-117">ID number to identify the session.</span></span> <span data-ttu-id="e860d-118">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e860d-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e860d-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-120"><strong>Einladen</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e860d-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="e860d-122">Uhrzeit der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e860d-122">Time of the first INVITE request.</span></span> <span data-ttu-id="e860d-123">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e860d-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e860d-124">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="e860d-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e860d-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e860d-127">URI der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="e860d-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-130">Typ des Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="e860d-130">Type of conference URI.</span></span> <span data-ttu-id="e860d-131">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e860d-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e860d-134">Bezeichner, der zwischen Instanzen von wiederkehrenden Konferenzen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="e860d-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="e860d-135">Jede wiederkehrende Konferenz Instanz hat dieselbe ConferenceURI, aber einen anderen ConfInstance-Wert.</span><span class="sxs-lookup"><span data-stu-id="e860d-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e860d-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e860d-138">URI des Konferenzservers</span><span class="sxs-lookup"><span data-stu-id="e860d-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-141">Der Typ des Konferenzserver-URIs.</span><span class="sxs-lookup"><span data-stu-id="e860d-141">Type of conferencing server URI.</span></span> <span data-ttu-id="e860d-142">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e860d-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e860d-145">Der URI des an der Sitzung beteiligten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e860d-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-148">Der Typ des URIs des Benutzers, dessen Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="e860d-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="e860d-149">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-152">Der Mandant des Benutzers, dessen Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="e860d-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="e860d-153">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e860d-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e860d-156">Eindeutiger Bezeichner des Benutzers, dessen Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="e860d-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-158">datetime</span><span class="sxs-lookup"><span data-stu-id="e860d-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="e860d-159">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e860d-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-162">Version des Konferenzservers</span><span class="sxs-lookup"><span data-stu-id="e860d-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-164">int</span><span class="sxs-lookup"><span data-stu-id="e860d-164">int</span></span></p></td>
<td><p><span data-ttu-id="e860d-165">Der Typ des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="e860d-165">Type of conference server.</span></span> <span data-ttu-id="e860d-166">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e860d-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e860d-169">Konferenzserver Kategorie.</span><span class="sxs-lookup"><span data-stu-id="e860d-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-172">Die Version des Clients, die von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-174">int</span><span class="sxs-lookup"><span data-stu-id="e860d-174">int</span></span></p></td>
<td><p><span data-ttu-id="e860d-175">Der Client, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="e860d-176">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e860d-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e860d-179">Der Name der Kategorie des Clients, der von dem Benutzer verwendet wurde, der Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="e860d-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e860d-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e860d-182">Der URI des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e860d-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-185">Der Typ des URIs des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e860d-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="e860d-186">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-189">Der Mandant des Benutzers, dessen Namen für die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e860d-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="e860d-190">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e860d-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e860d-193">Der URI des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-196">Der Typ des URIs des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="e860d-197">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-200">Der Mandant des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="e860d-201">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-202"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="e860d-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e860d-204">SIP-Dialogfeld-ID.</span><span class="sxs-lookup"><span data-stu-id="e860d-204">SIP dialog ID.</span></span> <span data-ttu-id="e860d-205">Das Format ist</span><span class="sxs-lookup"><span data-stu-id="e860d-205">The format is</span></span></p>
<p><span data-ttu-id="e860d-206">:d ialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="e860d-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-208">datetime</span><span class="sxs-lookup"><span data-stu-id="e860d-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="e860d-209">Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="e860d-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e860d-210">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-212">int</span><span class="sxs-lookup"><span data-stu-id="e860d-212">int</span></span></p></td>
<td><p><span data-ttu-id="e860d-213">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e860d-213">ID number to identify the session.</span></span> <span data-ttu-id="e860d-214">Wird in Verbindung mit ReplaceDialogIdTime verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e860d-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e860d-215">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e860d-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="e860d-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e860d-218">SIP-Dialog-ID, die die Sitzung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e860d-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="e860d-219">Das Format des is:</span><span class="sxs-lookup"><span data-stu-id="e860d-219">The format of the is:</span></span></p>
<p><span data-ttu-id="e860d-220">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="e860d-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-222">bit</span><span class="sxs-lookup"><span data-stu-id="e860d-222">bit</span></span></p></td>
<td><p><span data-ttu-id="e860d-223">Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e860d-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-225">bit</span><span class="sxs-lookup"><span data-stu-id="e860d-225">bit</span></span></p></td>
<td><p><span data-ttu-id="e860d-226">Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e860d-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-228">bit</span><span class="sxs-lookup"><span data-stu-id="e860d-228">bit</span></span></p></td>
<td><p><span data-ttu-id="e860d-229">Gibt an, ob sich der Benutzer vom internen Netzwerk anmeldet.</span><span class="sxs-lookup"><span data-stu-id="e860d-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-230"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-231">datetime</span><span class="sxs-lookup"><span data-stu-id="e860d-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="e860d-232">Zeitpunkt der Antwort auf die erste Einladungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="e860d-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="e860d-233">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e860d-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e860d-234">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="e860d-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-235"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-236">int</span><span class="sxs-lookup"><span data-stu-id="e860d-236">int</span></span></p></td>
<td><p><span data-ttu-id="e860d-237">SIP-Antwortcode für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="e860d-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="e860d-238">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e860d-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e860d-239">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="e860d-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-240"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-241">int</span><span class="sxs-lookup"><span data-stu-id="e860d-241">int</span></span></p></td>
<td><p><span data-ttu-id="e860d-242">Diagnose-ID, die aus Sitzungs-SIP-Headern erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="e860d-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-245">Inhaltstyp für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e860d-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-248">FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-251">Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="e860d-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-254">Vermittlungs Server, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-257">Gateway, das vom Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e860d-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e860d-260">Der FQDN des Edge-Servers, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e860d-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-262">smallint</span><span class="sxs-lookup"><span data-stu-id="e860d-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="e860d-263">Gibt die Attribute des Benutzers an, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="e860d-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="e860d-264">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="e860d-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="e860d-265">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="e860d-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e860d-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e860d-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e860d-267">smallint</span><span class="sxs-lookup"><span data-stu-id="e860d-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="e860d-268">Gibt die anrufattribute an.</span><span class="sxs-lookup"><span data-stu-id="e860d-268">Indicates the call attributes.</span></span> <span data-ttu-id="e860d-269">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="e860d-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e860d-270">0x01 – wiederholte Session0</span><span class="sxs-lookup"><span data-stu-id="e860d-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="e860d-271">x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="e860d-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

