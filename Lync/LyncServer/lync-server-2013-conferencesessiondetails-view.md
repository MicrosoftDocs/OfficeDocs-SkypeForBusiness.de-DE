---
title: 'Lync Server 2013: ConferenceSessionDetails-Ansicht'
description: 'Lync Server 2013: ConferenceSessionDetails-Ansicht.'
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
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566771"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="fbe11-103">ConferenceSessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbe11-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbe11-104">_**Letztes Änderungsstand des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="fbe11-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="fbe11-105">In der ConferenceSessionDetails-Ansicht werden Informationen zu mehrteiligen Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fbe11-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="fbe11-106">Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.</span><span class="sxs-lookup"><span data-stu-id="fbe11-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="fbe11-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fbe11-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe11-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="fbe11-108">Column</span></span></th>
<th><span data-ttu-id="fbe11-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="fbe11-109">Data Type</span></span></th>
<th><span data-ttu-id="fbe11-110">Details</span><span class="sxs-lookup"><span data-stu-id="fbe11-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fbe11-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="fbe11-113">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-113">Time of session request.</span></span> <span data-ttu-id="fbe11-114">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="fbe11-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fbe11-115">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-117">int</span><span class="sxs-lookup"><span data-stu-id="fbe11-117">int</span></span></p></td>
<td><p><span data-ttu-id="fbe11-118">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-118">ID number to identify the session.</span></span> <span data-ttu-id="fbe11-119">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fbe11-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="fbe11-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-121"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fbe11-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p104">Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird i. d. R. mit Daten aus der ersten INVITE-Nachricht in der Sitzung gefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) gefüllt.</span><span class="sxs-lookup"><span data-stu-id="fbe11-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-126"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fbe11-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-128">Die URI der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="fbe11-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-131">Typ des URI.</span><span class="sxs-lookup"><span data-stu-id="fbe11-131">Type of conference URI.</span></span> <span data-ttu-id="fbe11-132">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="fbe11-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p106">ID zur Unterscheidung zwischen einzelnen Instanzen wiederkehrender Konferenzen. Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.</span><span class="sxs-lookup"><span data-stu-id="fbe11-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fbe11-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-139">Der URI des Konferenz-Servers.</span><span class="sxs-lookup"><span data-stu-id="fbe11-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-142">Der Typ der Konferenz-Server-URIs.</span><span class="sxs-lookup"><span data-stu-id="fbe11-142">Type of conferencing server URI.</span></span> <span data-ttu-id="fbe11-143">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fbe11-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-146">Der URI des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-147"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-149">Der URI-Typ des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="fbe11-150">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-151"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-153">Der Mandant des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="fbe11-154">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-156">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="fbe11-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fbe11-157">Die eindeutige ID des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-159">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fbe11-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="fbe11-160">Die Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-163">Die Version des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="fbe11-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-165">int</span><span class="sxs-lookup"><span data-stu-id="fbe11-165">int</span></span></p></td>
<td><p><span data-ttu-id="fbe11-166">Der Typ des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="fbe11-166">Type of conference server.</span></span> <span data-ttu-id="fbe11-167">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fbe11-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-170">Die Kategorie des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="fbe11-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-173">Die Version des Clients für den Benutzer aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-175">int</span><span class="sxs-lookup"><span data-stu-id="fbe11-175">int</span></span></p></td>
<td><p><span data-ttu-id="fbe11-176">Der Client des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="fbe11-177">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fbe11-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-180">Der Name der Kategorie für den Client des Benutzers aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fbe11-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-183">Der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-186">Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="fbe11-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="fbe11-187">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-190">Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</span><span class="sxs-lookup"><span data-stu-id="fbe11-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="fbe11-191">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fbe11-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-194">URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="fbe11-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-197">Typ des URI des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="fbe11-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="fbe11-198">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-201">Mandant des Benutzers, der die Sitzung weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="fbe11-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="fbe11-202">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-203"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-204">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="fbe11-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p116">Die ID des SIP-Dialogs im Format</span><span class="sxs-lookup"><span data-stu-id="fbe11-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="fbe11-207">:d ialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="fbe11-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-209">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fbe11-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="fbe11-210">Die ID-Nummer zum Identifizieren des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="fbe11-211">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-213">int</span><span class="sxs-lookup"><span data-stu-id="fbe11-213">int</span></span></p></td>
<td><p><span data-ttu-id="fbe11-214">Die ID zur Identifizierung der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-214">ID number to identify the session.</span></span> <span data-ttu-id="fbe11-215">Wird zusammen mit ReplaceDialogIdTime verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="fbe11-216">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fbe11-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-218">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="fbe11-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p119">Die ID des SIP-Dialogs, der durch die Sitzung ersetzt wird im Format:</span><span class="sxs-lookup"><span data-stu-id="fbe11-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="fbe11-221">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="fbe11-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-223">Bit</span><span class="sxs-lookup"><span data-stu-id="fbe11-223">bit</span></span></p></td>
<td><p><span data-ttu-id="fbe11-224">Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-226">Bit</span><span class="sxs-lookup"><span data-stu-id="fbe11-226">bit</span></span></p></td>
<td><p><span data-ttu-id="fbe11-227">Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-229">Bit</span><span class="sxs-lookup"><span data-stu-id="fbe11-229">bit</span></span></p></td>
<td><p><span data-ttu-id="fbe11-230">Gibt an, ob sich der Benutzer aus dem internen Netzwerk angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="fbe11-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-231"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-232">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fbe11-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p120">Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fbe11-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-237">int</span><span class="sxs-lookup"><span data-stu-id="fbe11-237">int</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fbe11-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-241"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-242">int</span><span class="sxs-lookup"><span data-stu-id="fbe11-242">int</span></span></p></td>
<td><p><span data-ttu-id="fbe11-243">Die Diagnose-ID aus den SIP-Sitzungsheadern.</span><span class="sxs-lookup"><span data-stu-id="fbe11-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-246">Der Inhaltstyp der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fbe11-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-249">Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="fbe11-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-252">Der FQDN des Pools, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="fbe11-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-255">Der Vermittlungsserver, der vom Benutzer aus der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-256"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-258">Das Gateway, das vom Benutzer aus der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe11-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fbe11-261">Der FQDN des Edge-Servers, der vom Benutzer aus der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe11-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe11-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-263">smallint</span><span class="sxs-lookup"><span data-stu-id="fbe11-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p122">Gibt die Attribute des Benutzers aus der Sitzung an. Folgende Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="fbe11-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="fbe11-266">0x01 - Integriert in Standardtelefon</span><span class="sxs-lookup"><span data-stu-id="fbe11-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe11-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="fbe11-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe11-268">smallint</span><span class="sxs-lookup"><span data-stu-id="fbe11-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="fbe11-p123">Gibt die Anrufattribute an. Folgende Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="fbe11-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="fbe11-271">0x01 - Retried Session0</span><span class="sxs-lookup"><span data-stu-id="fbe11-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="fbe11-272">x02 - Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="fbe11-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

