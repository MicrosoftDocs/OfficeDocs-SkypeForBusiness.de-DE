---
title: 'Lync Server 2013: ConferenceSessionDetails-Tabelle'
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
ms.openlocfilehash: 6c88cb167f334bc27148b16deafb0e7759105955
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="85253-102">ConferenceSessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85253-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85253-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="85253-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="85253-104">Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.</span><span class="sxs-lookup"><span data-stu-id="85253-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85253-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="85253-105">Column</span></span></th>
<th><span data-ttu-id="85253-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="85253-106">Data Type</span></span></th>
<th><span data-ttu-id="85253-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="85253-107">Key/Index</span></span></th>
<th><span data-ttu-id="85253-108">Details</span><span class="sxs-lookup"><span data-stu-id="85253-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85253-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="85253-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="85253-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="85253-111">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-112">Zeitpunkt der Sitzungsanforderung; wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="85253-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="85253-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="85253-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-115">int</span><span class="sxs-lookup"><span data-stu-id="85253-115">int</span></span></p></td>
<td><p><span data-ttu-id="85253-116">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="85253-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="85253-117">ID number to identify the session.</span></span> <span data-ttu-id="85253-118">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="85253-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="85253-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-121">int</span><span class="sxs-lookup"><span data-stu-id="85253-121">int</span></span></p></td>
<td><p><span data-ttu-id="85253-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-123">Konferenz-URI mit Konferenzzustandsobjekt für diese Sitzung.</span><span class="sxs-lookup"><span data-stu-id="85253-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="85253-124">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="85253-125">Dieser URI ist ein auf dem Konferenzzustandsobjekt basierter Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="85253-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="85253-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="85253-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-128">ID, die Instanzen sich wiederholender Konferenzen voneinander unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="85253-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="85253-129">Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.</span><span class="sxs-lookup"><span data-stu-id="85253-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="85253-130">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="85253-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-132">int</span><span class="sxs-lookup"><span data-stu-id="85253-132">int</span></span></p></td>
<td><p><span data-ttu-id="85253-133">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-134">Konferenz-URI des Konferenzservers für diese Sitzung.</span><span class="sxs-lookup"><span data-stu-id="85253-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="85253-135">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="85253-136">Dieser URI ist der konferenzserverbasierte Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="85253-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="85253-137">Bei Konferenzsitzungen mit Konferenzzustandsobjekt ist diese Spalte NULL.</span><span class="sxs-lookup"><span data-stu-id="85253-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-139">int</span><span class="sxs-lookup"><span data-stu-id="85253-139">int</span></span></p></td>
<td><p><span data-ttu-id="85253-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-141">ID eines Benutzers in der Konferenzsitzung.</span><span class="sxs-lookup"><span data-stu-id="85253-141">ID of one user in the conference session.</span></span> <span data-ttu-id="85253-142">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="85253-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-p107">Eine GUID zur Identifikation der Instanz des Endpunkts. Wenn sich beispielsweise ein Benutzer auf verschiedenen Computern über dasselbe Konto anmeldet, erhält jeder Computer eine andere Endpunkt-ID.</span><span class="sxs-lookup"><span data-stu-id="85253-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-148">int</span><span class="sxs-lookup"><span data-stu-id="85253-148">int</span></span></p></td>
<td><p><span data-ttu-id="85253-149">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-150">Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird.</span><span class="sxs-lookup"><span data-stu-id="85253-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="85253-151">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="85253-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-153">int</span><span class="sxs-lookup"><span data-stu-id="85253-153">int</span></span></p></td>
<td><p><span data-ttu-id="85253-154">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-155">ID des Benutzers, der den Anruf weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="85253-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="85253-156">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-158">int</span><span class="sxs-lookup"><span data-stu-id="85253-158">int</span></span></p></td>
<td><p><span data-ttu-id="85253-159">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-160">Clientversion, die vom Konferenzbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85253-160">Client version used by the conference user.</span></span> <span data-ttu-id="85253-161">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-163">int</span><span class="sxs-lookup"><span data-stu-id="85253-163">int</span></span></p></td>
<td><p><span data-ttu-id="85253-164">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-165">Clientversion, die vom Konferenzserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85253-165">Client version used by the conference server.</span></span> <span data-ttu-id="85253-166">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="85253-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-168">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="85253-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="85253-169">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-170">ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="85253-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="85253-171">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="85253-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-173">int</span><span class="sxs-lookup"><span data-stu-id="85253-173">int</span></span></p></td>
<td><p><span data-ttu-id="85253-174">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-175">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="85253-175">ID number to identify the session.</span></span> <span data-ttu-id="85253-176">Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="85253-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="85253-177">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="85253-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-179">Bit</span><span class="sxs-lookup"><span data-stu-id="85253-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-180">Zeigt an, ob die Sitzung durch den A/V-Konferenzserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="85253-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="85253-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-182">Bit</span><span class="sxs-lookup"><span data-stu-id="85253-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-183">Zeigt an, ob die Sitzung durch den Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="85253-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="85253-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-185">Bit</span><span class="sxs-lookup"><span data-stu-id="85253-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-186">Tatsache, ob die Anmeldung des Benutzers intern erfolgte oder nicht.</span><span class="sxs-lookup"><span data-stu-id="85253-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="85253-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-188">int</span><span class="sxs-lookup"><span data-stu-id="85253-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-189">SIP-Antwortcode (Session Initiation Protocol) auf die Sitzungseinladung.</span><span class="sxs-lookup"><span data-stu-id="85253-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="85253-190">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="85253-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="85253-191">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="85253-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-192"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="85253-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-193">int</span><span class="sxs-lookup"><span data-stu-id="85253-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-194">Diagnose-ID aus dem SIP-Header.</span><span class="sxs-lookup"><span data-stu-id="85253-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-195"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="85253-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-196">int</span><span class="sxs-lookup"><span data-stu-id="85253-196">int</span></span></p></td>
<td><p><span data-ttu-id="85253-197">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-198">ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="85253-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="85253-199">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-200"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="85253-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-201">int</span><span class="sxs-lookup"><span data-stu-id="85253-201">int</span></span></p></td>
<td><p><span data-ttu-id="85253-202">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-203">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="85253-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="85253-204">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-206">int</span><span class="sxs-lookup"><span data-stu-id="85253-206">int</span></span></p></td>
<td><p><span data-ttu-id="85253-207">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-208">Der für den Anruf verwendete Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="85253-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="85253-209">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-210"><strong>Gatewayserver</strong></span><span class="sxs-lookup"><span data-stu-id="85253-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-211">int</span><span class="sxs-lookup"><span data-stu-id="85253-211">int</span></span></p></td>
<td><p><span data-ttu-id="85253-212">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-213">Das vom Anruf verwendete Gateway.</span><span class="sxs-lookup"><span data-stu-id="85253-213">The gateway the call is using.</span></span> <span data-ttu-id="85253-214">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-216">int</span><span class="sxs-lookup"><span data-stu-id="85253-216">int</span></span></p></td>
<td><p><span data-ttu-id="85253-217">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-218">Der vom Anruf verwendete Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="85253-218">The Edge Server the call is using.</span></span> <span data-ttu-id="85253-219">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-221">int</span><span class="sxs-lookup"><span data-stu-id="85253-221">int</span></span></p></td>
<td><p><span data-ttu-id="85253-222">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-223">In der Sitzung verwendeter Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="85253-223">Content type used in the session.</span></span> <span data-ttu-id="85253-224">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85253-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-225"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="85253-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-226">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="85253-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-p121">Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="85253-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-230"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="85253-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-231">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="85253-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-232">Die Uhrzeit der ersten SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="85253-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="85253-233">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="85253-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="85253-234">Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="85253-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="85253-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-236">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="85253-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-237">Der Zeitpunkt des Sitzungsendes.</span><span class="sxs-lookup"><span data-stu-id="85253-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="85253-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="85253-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="85253-240">Fremd</span><span class="sxs-lookup"><span data-stu-id="85253-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="85253-241">Enthält den MCU-URI-Typ-Wert aus der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="85253-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="85253-242">Dieses Feld dient zur Verbesserung der Abfrageleistung.</span><span class="sxs-lookup"><span data-stu-id="85253-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="85253-243">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="85253-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85253-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="85253-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-245">smallint</span><span class="sxs-lookup"><span data-stu-id="85253-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-p124">Ein Bitsatz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="85253-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="85253-248">Integrated with desktop phone - 1</span><span class="sxs-lookup"><span data-stu-id="85253-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85253-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="85253-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="85253-250">smallint</span><span class="sxs-lookup"><span data-stu-id="85253-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85253-p125">Ein Bitsatz, der die Anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="85253-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="85253-253">Retried Session - 1</span><span class="sxs-lookup"><span data-stu-id="85253-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85253-254">\*Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="85253-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="85253-255">Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.</span><span class="sxs-lookup"><span data-stu-id="85253-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

