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
ms.openlocfilehash: f7f0907b6c92d3ca5ed1adf7f1a991242d6ddeb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="f4499-102">ConferenceSessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4499-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4499-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f4499-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f4499-104">Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.</span><span class="sxs-lookup"><span data-stu-id="f4499-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4499-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="f4499-105">Column</span></span></th>
<th><span data-ttu-id="f4499-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f4499-106">Data Type</span></span></th>
<th><span data-ttu-id="f4499-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="f4499-107">Key/Index</span></span></th>
<th><span data-ttu-id="f4499-108">Details</span><span class="sxs-lookup"><span data-stu-id="f4499-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4499-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="f4499-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="f4499-111">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-112">Zeitpunkt der Sitzungsanforderung; wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f4499-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="f4499-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-115">int</span><span class="sxs-lookup"><span data-stu-id="f4499-115">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-116">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="f4499-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f4499-117">ID number to identify the session.</span></span> <span data-ttu-id="f4499-118">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f4499-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="f4499-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-121">int</span><span class="sxs-lookup"><span data-stu-id="f4499-121">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-123">Konferenz-URI mit Konferenzzustandsobjekt für diese Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f4499-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="f4499-124">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f4499-125">Dieser URI ist ein auf dem Konferenzzustandsobjekt basierter Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="f4499-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="f4499-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-128">ID, die Instanzen sich wiederholender Konferenzen voneinander unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="f4499-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="f4499-129">Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.</span><span class="sxs-lookup"><span data-stu-id="f4499-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="f4499-130">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f4499-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-132">int</span><span class="sxs-lookup"><span data-stu-id="f4499-132">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-133">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-134">Konferenz-URI des Konferenzservers für diese Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f4499-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="f4499-135">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f4499-136">Dieser URI ist der konferenzserverbasierte Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="f4499-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="f4499-137">Bei Konferenzsitzungen mit Konferenzzustandsobjekt ist diese Spalte NULL.</span><span class="sxs-lookup"><span data-stu-id="f4499-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-139">int</span><span class="sxs-lookup"><span data-stu-id="f4499-139">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-141">ID eines Benutzers in der Konferenzsitzung.</span><span class="sxs-lookup"><span data-stu-id="f4499-141">ID of one user in the conference session.</span></span> <span data-ttu-id="f4499-142">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f4499-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-p107">Eine GUID zur Identifikation der Instanz des Endpunkts. Wenn sich beispielsweise ein Benutzer auf verschiedenen Computern über dasselbe Konto anmeldet, erhält jeder Computer eine andere Endpunkt-ID.</span><span class="sxs-lookup"><span data-stu-id="f4499-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-148">int</span><span class="sxs-lookup"><span data-stu-id="f4499-148">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-149">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-150">Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird.</span><span class="sxs-lookup"><span data-stu-id="f4499-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="f4499-151">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-153">int</span><span class="sxs-lookup"><span data-stu-id="f4499-153">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-154">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-155">ID des Benutzers, der den Anruf weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="f4499-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="f4499-156">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-158">int</span><span class="sxs-lookup"><span data-stu-id="f4499-158">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-159">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-160">Clientversion, die vom Konferenzbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4499-160">Client version used by the conference user.</span></span> <span data-ttu-id="f4499-161">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-163">int</span><span class="sxs-lookup"><span data-stu-id="f4499-163">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-164">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-165">Clientversion, die vom Konferenzserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4499-165">Client version used by the conference server.</span></span> <span data-ttu-id="f4499-166">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-168">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f4499-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="f4499-169">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-170">ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="f4499-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="f4499-171">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-173">int</span><span class="sxs-lookup"><span data-stu-id="f4499-173">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-174">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-175">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f4499-175">ID number to identify the session.</span></span> <span data-ttu-id="f4499-176">Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="f4499-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="f4499-177">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-179">Bit</span><span class="sxs-lookup"><span data-stu-id="f4499-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-180">Zeigt an, ob die Sitzung durch den A/V-Konferenzserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4499-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-182">Bit</span><span class="sxs-lookup"><span data-stu-id="f4499-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-183">Zeigt an, ob die Sitzung durch den Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4499-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-185">Bit</span><span class="sxs-lookup"><span data-stu-id="f4499-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-186">Tatsache, ob die Anmeldung des Benutzers intern erfolgte oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f4499-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-188">int</span><span class="sxs-lookup"><span data-stu-id="f4499-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-189">SIP-Antwortcode (Session Initiation Protocol) auf die Sitzungseinladung.</span><span class="sxs-lookup"><span data-stu-id="f4499-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="f4499-190">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="f4499-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f4499-191">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="f4499-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-192"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-193">int</span><span class="sxs-lookup"><span data-stu-id="f4499-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-194">Diagnose-ID aus dem SIP-Header.</span><span class="sxs-lookup"><span data-stu-id="f4499-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-195"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-196">int</span><span class="sxs-lookup"><span data-stu-id="f4499-196">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-197">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-198">ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="f4499-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="f4499-199">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-200"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-201">int</span><span class="sxs-lookup"><span data-stu-id="f4499-201">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-202">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-203">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="f4499-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="f4499-204">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-206">int</span><span class="sxs-lookup"><span data-stu-id="f4499-206">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-207">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-208">Der für den Anruf verwendete Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="f4499-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="f4499-209">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-210"><strong>Gatewayserver</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-211">int</span><span class="sxs-lookup"><span data-stu-id="f4499-211">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-212">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-213">Das vom Anruf verwendete Gateway.</span><span class="sxs-lookup"><span data-stu-id="f4499-213">The gateway the call is using.</span></span> <span data-ttu-id="f4499-214">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-216">int</span><span class="sxs-lookup"><span data-stu-id="f4499-216">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-217">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-218">Der vom Anruf verwendete Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="f4499-218">The Edge Server the call is using.</span></span> <span data-ttu-id="f4499-219">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-221">int</span><span class="sxs-lookup"><span data-stu-id="f4499-221">int</span></span></p></td>
<td><p><span data-ttu-id="f4499-222">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-223">In der Sitzung verwendeter Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="f4499-223">Content type used in the session.</span></span> <span data-ttu-id="f4499-224">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4499-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-225"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-226">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f4499-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-p121">Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="f4499-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-230"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-231">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f4499-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-232">Die Uhrzeit der ersten SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="f4499-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="f4499-233">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="f4499-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f4499-234">Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="f4499-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-236">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f4499-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-237">Der Zeitpunkt des Sitzungsendes.</span><span class="sxs-lookup"><span data-stu-id="f4499-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="f4499-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4499-240">Fremd</span><span class="sxs-lookup"><span data-stu-id="f4499-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4499-241">Enthält den MCU-URI-Typ-Wert aus der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f4499-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="f4499-242">Dieses Feld dient zur Verbesserung der Abfrageleistung.</span><span class="sxs-lookup"><span data-stu-id="f4499-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="f4499-243">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f4499-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4499-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-245">smallint</span><span class="sxs-lookup"><span data-stu-id="f4499-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-p124">Ein Bitsatz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="f4499-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="f4499-248">Integrated with desktop phone - 1</span><span class="sxs-lookup"><span data-stu-id="f4499-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4499-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f4499-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f4499-250">smallint</span><span class="sxs-lookup"><span data-stu-id="f4499-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4499-p125">Ein Bitsatz, der die Anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="f4499-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="f4499-253">Retried Session - 1</span><span class="sxs-lookup"><span data-stu-id="f4499-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f4499-254">\*Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="f4499-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="f4499-255">Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.</span><span class="sxs-lookup"><span data-stu-id="f4499-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

