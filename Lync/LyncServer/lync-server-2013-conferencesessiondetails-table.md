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
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="ec306-102">ConferenceSessionDetails-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec306-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec306-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ec306-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ec306-104">Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann.</span><span class="sxs-lookup"><span data-stu-id="ec306-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec306-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="ec306-105">Column</span></span></th>
<th><span data-ttu-id="ec306-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ec306-106">Data Type</span></span></th>
<th><span data-ttu-id="ec306-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="ec306-107">Key/Index</span></span></th>
<th><span data-ttu-id="ec306-108">Details</span><span class="sxs-lookup"><span data-stu-id="ec306-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec306-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="ec306-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="ec306-111">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-112">Uhrzeit der Sitzungsanforderung; wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ec306-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="ec306-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-115">int</span><span class="sxs-lookup"><span data-stu-id="ec306-115">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-116">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-117">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ec306-117">ID number to identify the session.</span></span> <span data-ttu-id="ec306-118">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Konferenzsitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ec306-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="ec306-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-121">int</span><span class="sxs-lookup"><span data-stu-id="ec306-121">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-123">Fokus Konferenz-URI, der sich auf diese Sitzung bezieht.</span><span class="sxs-lookup"><span data-stu-id="ec306-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="ec306-124">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ec306-125">Dieser URI ist ein Fokus basierter Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="ec306-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="ec306-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-128">Bezeichner, der zwischen Instanzen von wiederkehrenden Konferenzen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="ec306-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="ec306-129">Jede wiederkehrende Konferenz Instanz hat dieselbe ConferenceURI, aber einen anderen ConfInstance-Wert.</span><span class="sxs-lookup"><span data-stu-id="ec306-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="ec306-130">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ec306-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-132">int</span><span class="sxs-lookup"><span data-stu-id="ec306-132">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-133">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-134">Konferenzserver-Konferenz-URI, der sich auf diese Sitzung bezieht.</span><span class="sxs-lookup"><span data-stu-id="ec306-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="ec306-135">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ec306-136">Dieser URI ist der Konferenz-serverbasierte Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="ec306-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="ec306-137">Für Konferenzsitzungen mit Fokus ist diese Spalte NULL.</span><span class="sxs-lookup"><span data-stu-id="ec306-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-138"><strong>UserID</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-139">int</span><span class="sxs-lookup"><span data-stu-id="ec306-139">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-141">Die ID eines Benutzers in der Konferenzsitzung.</span><span class="sxs-lookup"><span data-stu-id="ec306-141">ID of one user in the conference session.</span></span> <span data-ttu-id="ec306-142">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ec306-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-145">Eine GUID zum Identifizieren der Instanz des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="ec306-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="ec306-146">Wenn sich ein Benutzer beispielsweise an verschiedenen Computern mit demselben Konto anmeldet, verfügt jeder Computer über eine andere Endpunkt-ID.</span><span class="sxs-lookup"><span data-stu-id="ec306-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-148">int</span><span class="sxs-lookup"><span data-stu-id="ec306-148">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-149">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-150">Gibt die ID des Benutzers an, der der Anrufer im Auftrag ist.</span><span class="sxs-lookup"><span data-stu-id="ec306-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="ec306-151">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-153">int</span><span class="sxs-lookup"><span data-stu-id="ec306-153">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-154">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-155">Die ID des Benutzers, auf den der Anruf verweist.</span><span class="sxs-lookup"><span data-stu-id="ec306-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="ec306-156">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-158">int</span><span class="sxs-lookup"><span data-stu-id="ec306-158">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-159">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-160">Vom Konferenzbenutzer verwendete Client Version.</span><span class="sxs-lookup"><span data-stu-id="ec306-160">Client version used by the conference user.</span></span> <span data-ttu-id="ec306-161">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-163">int</span><span class="sxs-lookup"><span data-stu-id="ec306-163">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-164">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-165">Client Version, die vom Konferenzserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec306-165">Client version used by the conference server.</span></span> <span data-ttu-id="ec306-166">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-168">datetime</span><span class="sxs-lookup"><span data-stu-id="ec306-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="ec306-169">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-170">Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ec306-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="ec306-171">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-173">int</span><span class="sxs-lookup"><span data-stu-id="ec306-173">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-174">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-175">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ec306-175">ID number to identify the session.</span></span> <span data-ttu-id="ec306-176">Wird in Verbindung mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ec306-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="ec306-177">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-179">bit</span><span class="sxs-lookup"><span data-stu-id="ec306-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-180">Gibt an, ob die Sitzung vom Konferenz Server gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ec306-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-182">bit</span><span class="sxs-lookup"><span data-stu-id="ec306-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-183">Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ec306-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-185">bit</span><span class="sxs-lookup"><span data-stu-id="ec306-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-186">Ob der Benutzer intern angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ec306-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-187"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-188">int</span><span class="sxs-lookup"><span data-stu-id="ec306-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-189">SIP-Antwortcode (Session Initiation Protocol) für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="ec306-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="ec306-190">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ec306-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ec306-191">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="ec306-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-192"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-193">int</span><span class="sxs-lookup"><span data-stu-id="ec306-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-194">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="ec306-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-195"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-196">int</span><span class="sxs-lookup"><span data-stu-id="ec306-196">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-197">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-198">Die ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="ec306-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="ec306-199">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-200"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-201">int</span><span class="sxs-lookup"><span data-stu-id="ec306-201">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-202">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-203">Die ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="ec306-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="ec306-204">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-206">int</span><span class="sxs-lookup"><span data-stu-id="ec306-206">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-207">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-208">Der Vermittlungs Server, den der Anruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec306-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="ec306-209">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-210"><strong>Gatewayserver</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-211">int</span><span class="sxs-lookup"><span data-stu-id="ec306-211">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-212">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-213">Das Gateway, das der Anruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec306-213">The gateway the call is using.</span></span> <span data-ttu-id="ec306-214">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-216">int</span><span class="sxs-lookup"><span data-stu-id="ec306-216">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-217">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-218">Der Edge-Server, den der Anruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec306-218">The Edge Server the call is using.</span></span> <span data-ttu-id="ec306-219">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-220"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-221">int</span><span class="sxs-lookup"><span data-stu-id="ec306-221">int</span></span></p></td>
<td><p><span data-ttu-id="ec306-222">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-223">Inhaltstyp, der in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec306-223">Content type used in the session.</span></span> <span data-ttu-id="ec306-224">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der Tabelle "ContentTypes" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ec306-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-225"><strong>Einladen</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-226">datetime</span><span class="sxs-lookup"><span data-stu-id="ec306-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-227">Der Zeitpunkt der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ec306-227">The time of the first INVITE request.</span></span> <span data-ttu-id="ec306-228">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ec306-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ec306-229">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="ec306-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-230"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-231">datetime</span><span class="sxs-lookup"><span data-stu-id="ec306-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-232">Zeitpunkt der ersten SIP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="ec306-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="ec306-233">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ec306-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ec306-234">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="ec306-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-236">datetime</span><span class="sxs-lookup"><span data-stu-id="ec306-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-237">Der Zeitpunkt, zu dem die Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec306-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="ec306-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ec306-240">Fremd</span><span class="sxs-lookup"><span data-stu-id="ec306-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec306-241">Enthält den Wert des MCU-URI-Typs aus der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ec306-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="ec306-242">Dieses Feld wird verwendet, um die Abfrageleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ec306-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="ec306-243">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ec306-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec306-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-245">smallint</span><span class="sxs-lookup"><span data-stu-id="ec306-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-246">Ein Bit-Satz, der die Benutzerattribute angibt.</span><span class="sxs-lookup"><span data-stu-id="ec306-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="ec306-247">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="ec306-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ec306-248">Integriert mit dem Desktop-Telefon-1</span><span class="sxs-lookup"><span data-stu-id="ec306-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec306-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ec306-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ec306-250">smallint</span><span class="sxs-lookup"><span data-stu-id="ec306-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec306-251">Ein Bit-Satz, der die anrufattribute angibt.</span><span class="sxs-lookup"><span data-stu-id="ec306-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="ec306-252">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="ec306-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ec306-253">Wiederholte Sitzung – 1</span><span class="sxs-lookup"><span data-stu-id="ec306-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ec306-254">\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1.</span><span class="sxs-lookup"><span data-stu-id="ec306-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="ec306-255">Wenn mehrere Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, für einen anderen wird 2 usw.</span><span class="sxs-lookup"><span data-stu-id="ec306-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

