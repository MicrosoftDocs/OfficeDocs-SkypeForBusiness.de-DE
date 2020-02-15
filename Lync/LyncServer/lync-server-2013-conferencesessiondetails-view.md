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
ms.openlocfilehash: be9d3566a951ee1b65d87e423627f556254173b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="356de-102">ConferenceSessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="356de-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="356de-103">_**Letztes Änderungsstand des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="356de-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="356de-104">In der ConferenceSessionDetails-Ansicht werden Informationen zu mehrteiligen Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="356de-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="356de-105">Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.</span><span class="sxs-lookup"><span data-stu-id="356de-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="356de-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="356de-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="356de-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="356de-107">Column</span></span></th>
<th><span data-ttu-id="356de-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="356de-108">Data Type</span></span></th>
<th><span data-ttu-id="356de-109">Details</span><span class="sxs-lookup"><span data-stu-id="356de-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="356de-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="356de-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="356de-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="356de-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="356de-112">Time of session request.</span></span> <span data-ttu-id="356de-113">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="356de-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="356de-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="356de-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-116">int</span><span class="sxs-lookup"><span data-stu-id="356de-116">int</span></span></p></td>
<td><p><span data-ttu-id="356de-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-117">ID number to identify the session.</span></span> <span data-ttu-id="356de-118">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="356de-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="356de-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-120"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="356de-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="356de-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="356de-p104">Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird i. d. R. mit Daten aus der ersten INVITE-Nachricht in der Sitzung gefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) gefüllt.</span><span class="sxs-lookup"><span data-stu-id="356de-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="356de-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="356de-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="356de-127">Die URI der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="356de-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-130">Typ des URI.</span><span class="sxs-lookup"><span data-stu-id="356de-130">Type of conference URI.</span></span> <span data-ttu-id="356de-131">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="356de-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="356de-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="356de-p106">ID zur Unterscheidung zwischen einzelnen Instanzen wiederkehrender Konferenzen. Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.</span><span class="sxs-lookup"><span data-stu-id="356de-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="356de-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="356de-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="356de-138">Der URI des Konferenz-Servers.</span><span class="sxs-lookup"><span data-stu-id="356de-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-141">Der Typ der Konferenz-Server-URIs.</span><span class="sxs-lookup"><span data-stu-id="356de-141">Type of conferencing server URI.</span></span> <span data-ttu-id="356de-142">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="356de-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="356de-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="356de-145">Der URI des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-148">Der URI-Typ des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="356de-149">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="356de-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-152">Der Mandant des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="356de-153">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="356de-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="356de-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="356de-156">Die eindeutige ID des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="356de-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-158">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="356de-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="356de-159">Die Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="356de-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-162">Die Version des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="356de-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-164">int</span><span class="sxs-lookup"><span data-stu-id="356de-164">int</span></span></p></td>
<td><p><span data-ttu-id="356de-165">Der Typ des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="356de-165">Type of conference server.</span></span> <span data-ttu-id="356de-166">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="356de-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="356de-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="356de-169">Die Kategorie des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="356de-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="356de-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-172">Die Version des Clients für den Benutzer aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-174">int</span><span class="sxs-lookup"><span data-stu-id="356de-174">int</span></span></p></td>
<td><p><span data-ttu-id="356de-175">Der Client des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="356de-176">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="356de-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="356de-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="356de-179">Der Name der Kategorie für den Client des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="356de-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="356de-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="356de-182">Der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-185">Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="356de-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="356de-186">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="356de-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-189">Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="356de-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="356de-190">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="356de-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="356de-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="356de-193">URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="356de-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-196">Typ des URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="356de-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="356de-197">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="356de-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-200">Mandant des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="356de-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="356de-201">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-202"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="356de-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="356de-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="356de-p116">Die ID des SIP-Dialogs im Format</span><span class="sxs-lookup"><span data-stu-id="356de-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="356de-206">:d ialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="356de-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="356de-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-208">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="356de-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="356de-209">Die ID-Nummer zum Identifizieren des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="356de-210">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="356de-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-212">int</span><span class="sxs-lookup"><span data-stu-id="356de-212">int</span></span></p></td>
<td><p><span data-ttu-id="356de-213">Die ID zur Identifizierung der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-213">ID number to identify the session.</span></span> <span data-ttu-id="356de-214">Wird zusammen mit ReplaceDialogIdTime verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="356de-215">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="356de-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="356de-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="356de-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="356de-p119">Die ID des SIP-Dialogs, der durch die Sitzung ersetzt wird im Format:</span><span class="sxs-lookup"><span data-stu-id="356de-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="356de-220">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="356de-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="356de-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-222">Bit</span><span class="sxs-lookup"><span data-stu-id="356de-222">bit</span></span></p></td>
<td><p><span data-ttu-id="356de-223">Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="356de-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-225">Bit</span><span class="sxs-lookup"><span data-stu-id="356de-225">bit</span></span></p></td>
<td><p><span data-ttu-id="356de-226">Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="356de-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-228">Bit</span><span class="sxs-lookup"><span data-stu-id="356de-228">bit</span></span></p></td>
<td><p><span data-ttu-id="356de-229">Gibt an, ob sich der Benutzer aus dem internen Netzwerk angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="356de-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-230"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="356de-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-231">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="356de-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="356de-p120">Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="356de-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="356de-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-236">int</span><span class="sxs-lookup"><span data-stu-id="356de-236">int</span></span></p></td>
<td><p><span data-ttu-id="356de-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="356de-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-240"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="356de-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-241">int</span><span class="sxs-lookup"><span data-stu-id="356de-241">int</span></span></p></td>
<td><p><span data-ttu-id="356de-242">Die Diagnose-ID aus den SIP-Sitzungsheadern.</span><span class="sxs-lookup"><span data-stu-id="356de-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="356de-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-245">Der Inhaltstyp der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="356de-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-246"><strong>Frontend</strong></span><span class="sxs-lookup"><span data-stu-id="356de-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-248">Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="356de-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="356de-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-251">Der FQDN des Pools, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="356de-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="356de-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-254">Der Vermittlungsserver, der vom Benutzer aus der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="356de-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-257">Das Gateway, das vom Benutzer aus der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="356de-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="356de-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="356de-260">Der FQDN des Edge-Servers, der vom Benutzer aus der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="356de-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356de-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="356de-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-262">smallint</span><span class="sxs-lookup"><span data-stu-id="356de-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="356de-p122">Gibt die Attribute des Benutzers aus der Sitzung an. Folgende Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="356de-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="356de-265">0x01 - Integriert in Standardtelefon</span><span class="sxs-lookup"><span data-stu-id="356de-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356de-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="356de-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="356de-267">smallint</span><span class="sxs-lookup"><span data-stu-id="356de-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="356de-p123">Gibt die Anrufattribute an. Folgende Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="356de-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="356de-270">0x01 - Retried Session0</span><span class="sxs-lookup"><span data-stu-id="356de-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="356de-271">x02 - Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="356de-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

