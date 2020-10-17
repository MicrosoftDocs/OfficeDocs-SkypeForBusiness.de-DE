---
title: 'Lync Server 2013: ConferenceSessionDetails-Tabelle'
description: 'Lync Server 2013: ConferenceSessionDetails-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566781"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="42110-103">ConferenceSessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42110-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42110-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="42110-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="42110-105">Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.</span><span class="sxs-lookup"><span data-stu-id="42110-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42110-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="42110-106">Column</span></span></th>
<th><span data-ttu-id="42110-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="42110-107">Data Type</span></span></th>
<th><span data-ttu-id="42110-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="42110-108">Key/Index</span></span></th>
<th><span data-ttu-id="42110-109">Details</span><span class="sxs-lookup"><span data-stu-id="42110-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42110-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="42110-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="42110-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="42110-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-113">Zeitpunkt der Sitzungsanforderung; wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="42110-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="42110-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="42110-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-116">int</span><span class="sxs-lookup"><span data-stu-id="42110-116">int</span></span></p></td>
<td><p><span data-ttu-id="42110-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-118">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="42110-118">ID number to identify the session.</span></span> <span data-ttu-id="42110-119">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="42110-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="42110-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-122">int</span><span class="sxs-lookup"><span data-stu-id="42110-122">int</span></span></p></td>
<td><p><span data-ttu-id="42110-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-124">Konferenz-URI mit Konferenzzustandsobjekt für diese Sitzung.</span><span class="sxs-lookup"><span data-stu-id="42110-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="42110-125">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="42110-126">Dieser URI ist ein auf dem Konferenzzustandsobjekt basierter Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="42110-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="42110-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-128">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="42110-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-129">ID, die Instanzen sich wiederholender Konferenzen voneinander unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="42110-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="42110-130">Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.</span><span class="sxs-lookup"><span data-stu-id="42110-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="42110-131">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="42110-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-133">int</span><span class="sxs-lookup"><span data-stu-id="42110-133">int</span></span></p></td>
<td><p><span data-ttu-id="42110-134">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-135">Konferenz-URI des Konferenzservers für diese Sitzung.</span><span class="sxs-lookup"><span data-stu-id="42110-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="42110-136">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="42110-137">Dieser URI ist der konferenzserverbasierte Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="42110-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="42110-138">Bei Konferenzsitzungen mit Konferenzzustandsobjekt ist diese Spalte NULL.</span><span class="sxs-lookup"><span data-stu-id="42110-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-140">int</span><span class="sxs-lookup"><span data-stu-id="42110-140">int</span></span></p></td>
<td><p><span data-ttu-id="42110-141">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-142">ID eines Benutzers in der Konferenzsitzung.</span><span class="sxs-lookup"><span data-stu-id="42110-142">ID of one user in the conference session.</span></span> <span data-ttu-id="42110-143">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-145">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="42110-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-p107">Eine GUID zur Identifikation der Instanz des Endpunkts. Wenn sich beispielsweise ein Benutzer auf verschiedenen Computern über dasselbe Konto anmeldet, erhält jeder Computer eine andere Endpunkt-ID.</span><span class="sxs-lookup"><span data-stu-id="42110-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-149">int</span><span class="sxs-lookup"><span data-stu-id="42110-149">int</span></span></p></td>
<td><p><span data-ttu-id="42110-150">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-151">Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird.</span><span class="sxs-lookup"><span data-stu-id="42110-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="42110-152">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="42110-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-154">int</span><span class="sxs-lookup"><span data-stu-id="42110-154">int</span></span></p></td>
<td><p><span data-ttu-id="42110-155">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-156">ID des Benutzers, der den Anruf weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="42110-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="42110-157">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-159">int</span><span class="sxs-lookup"><span data-stu-id="42110-159">int</span></span></p></td>
<td><p><span data-ttu-id="42110-160">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-161">Clientversion, die vom Konferenzbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42110-161">Client version used by the conference user.</span></span> <span data-ttu-id="42110-162">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-164">int</span><span class="sxs-lookup"><span data-stu-id="42110-164">int</span></span></p></td>
<td><p><span data-ttu-id="42110-165">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-166">Clientversion, die vom Konferenzserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42110-166">Client version used by the conference server.</span></span> <span data-ttu-id="42110-167">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="42110-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-169">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="42110-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="42110-170">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-171">ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="42110-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="42110-172">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="42110-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-174">int</span><span class="sxs-lookup"><span data-stu-id="42110-174">int</span></span></p></td>
<td><p><span data-ttu-id="42110-175">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-176">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="42110-176">ID number to identify the session.</span></span> <span data-ttu-id="42110-177">Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="42110-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="42110-178">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="42110-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-180">Bit</span><span class="sxs-lookup"><span data-stu-id="42110-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-181">Zeigt an, ob die Sitzung durch den A/V-Konferenzserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="42110-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="42110-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-183">Bit</span><span class="sxs-lookup"><span data-stu-id="42110-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-184">Zeigt an, ob die Sitzung durch den Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="42110-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="42110-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-186">Bit</span><span class="sxs-lookup"><span data-stu-id="42110-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-187">Tatsache, ob die Anmeldung des Benutzers intern erfolgte oder nicht.</span><span class="sxs-lookup"><span data-stu-id="42110-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="42110-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-189">int</span><span class="sxs-lookup"><span data-stu-id="42110-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-190">SIP-Antwortcode (Session Initiation Protocol) auf die Sitzungseinladung.</span><span class="sxs-lookup"><span data-stu-id="42110-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="42110-191">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="42110-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="42110-192">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="42110-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-193"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="42110-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-194">int</span><span class="sxs-lookup"><span data-stu-id="42110-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-195">Diagnose-ID aus dem SIP-Header.</span><span class="sxs-lookup"><span data-stu-id="42110-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-196"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="42110-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-197">int</span><span class="sxs-lookup"><span data-stu-id="42110-197">int</span></span></p></td>
<td><p><span data-ttu-id="42110-198">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-199">ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="42110-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="42110-200">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-201"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="42110-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-202">int</span><span class="sxs-lookup"><span data-stu-id="42110-202">int</span></span></p></td>
<td><p><span data-ttu-id="42110-203">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-204">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="42110-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="42110-205">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-207">int</span><span class="sxs-lookup"><span data-stu-id="42110-207">int</span></span></p></td>
<td><p><span data-ttu-id="42110-208">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-209">Der für den Anruf verwendete Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="42110-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="42110-210">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-211"><strong>Gatewayserver</strong></span><span class="sxs-lookup"><span data-stu-id="42110-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-212">int</span><span class="sxs-lookup"><span data-stu-id="42110-212">int</span></span></p></td>
<td><p><span data-ttu-id="42110-213">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-214">Das vom Anruf verwendete Gateway.</span><span class="sxs-lookup"><span data-stu-id="42110-214">The gateway the call is using.</span></span> <span data-ttu-id="42110-215">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-217">int</span><span class="sxs-lookup"><span data-stu-id="42110-217">int</span></span></p></td>
<td><p><span data-ttu-id="42110-218">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-219">Der vom Anruf verwendete Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="42110-219">The Edge Server the call is using.</span></span> <span data-ttu-id="42110-220">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-222">int</span><span class="sxs-lookup"><span data-stu-id="42110-222">int</span></span></p></td>
<td><p><span data-ttu-id="42110-223">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-224">In der Sitzung verwendeter Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="42110-224">Content type used in the session.</span></span> <span data-ttu-id="42110-225">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42110-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-226"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="42110-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-227">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="42110-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-p121">Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="42110-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-231"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="42110-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-232">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="42110-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-233">Die Uhrzeit der ersten SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="42110-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="42110-234">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="42110-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="42110-235">Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="42110-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="42110-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-237">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="42110-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-238">Der Zeitpunkt des Sitzungsendes.</span><span class="sxs-lookup"><span data-stu-id="42110-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="42110-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="42110-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="42110-241">Fremd</span><span class="sxs-lookup"><span data-stu-id="42110-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42110-242">Enthält den MCU-URI-Typ-Wert aus der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="42110-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="42110-243">Dieses Feld dient zur Verbesserung der Abfrageleistung.</span><span class="sxs-lookup"><span data-stu-id="42110-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="42110-244">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="42110-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42110-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="42110-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-246">smallint</span><span class="sxs-lookup"><span data-stu-id="42110-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-p124">Ein Bitsatz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="42110-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="42110-249">Integrated with desktop phone - 1</span><span class="sxs-lookup"><span data-stu-id="42110-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42110-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="42110-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="42110-251">smallint</span><span class="sxs-lookup"><span data-stu-id="42110-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42110-p125">Ein Bitsatz, der die Anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="42110-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="42110-254">Retried Session - 1</span><span class="sxs-lookup"><span data-stu-id="42110-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42110-255">\* Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="42110-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="42110-256">Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.</span><span class="sxs-lookup"><span data-stu-id="42110-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

