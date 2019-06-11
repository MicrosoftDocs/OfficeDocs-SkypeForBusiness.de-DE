---
title: 'Lync Server 2013: ConferenceSessionDetails-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="00c0c-102">ConferenceSessionDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00c0c-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00c0c-103">_**Letztes Änderungsdatum des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="00c0c-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="00c0c-104">In der ConferenceSessionDetails-Ansicht werden Informationen zu mehrteiligen Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00c0c-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="00c0c-105">Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann.</span><span class="sxs-lookup"><span data-stu-id="00c0c-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="00c0c-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00c0c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00c0c-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="00c0c-107">Column</span></span></th>
<th><span data-ttu-id="00c0c-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="00c0c-108">Data Type</span></span></th>
<th><span data-ttu-id="00c0c-109">Details</span><span class="sxs-lookup"><span data-stu-id="00c0c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="00c0c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="00c0c-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="00c0c-112">Time of session request.</span></span> <span data-ttu-id="00c0c-113">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00c0c-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="00c0c-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-116">int</span><span class="sxs-lookup"><span data-stu-id="00c0c-116">int</span></span></p></td>
<td><p><span data-ttu-id="00c0c-117">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00c0c-117">ID number to identify the session.</span></span> <span data-ttu-id="00c0c-118">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00c0c-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="00c0c-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-120"><strong>Einladen</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-121">datetime</span><span class="sxs-lookup"><span data-stu-id="00c0c-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="00c0c-122">Uhrzeit der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="00c0c-122">Time of the first INVITE request.</span></span> <span data-ttu-id="00c0c-123">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="00c0c-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="00c0c-124">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="00c0c-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="00c0c-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-127">URI der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="00c0c-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-130">Typ des Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="00c0c-130">Type of conference URI.</span></span> <span data-ttu-id="00c0c-131">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="00c0c-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="00c0c-134">Bezeichner, der zwischen Instanzen von wiederkehrenden Konferenzen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="00c0c-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="00c0c-135">Jede wiederkehrende Konferenz Instanz hat dieselbe ConferenceURI, aber einen anderen ConfInstance-Wert.</span><span class="sxs-lookup"><span data-stu-id="00c0c-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="00c0c-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-138">URI des Konferenzservers</span><span class="sxs-lookup"><span data-stu-id="00c0c-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-141">Der Typ des Konferenzserver-URIs.</span><span class="sxs-lookup"><span data-stu-id="00c0c-141">Type of conferencing server URI.</span></span> <span data-ttu-id="00c0c-142">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="00c0c-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-145">Der URI des an der Sitzung beteiligten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="00c0c-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-148">Der Typ des URIs des Benutzers, dessen Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="00c0c-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="00c0c-149">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-152">Der Mandant des Benutzers, dessen Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="00c0c-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="00c0c-153">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="00c0c-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="00c0c-156">Eindeutiger Bezeichner des Benutzers, dessen Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="00c0c-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-158">datetime</span><span class="sxs-lookup"><span data-stu-id="00c0c-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="00c0c-159">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="00c0c-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-162">Version des Konferenzservers</span><span class="sxs-lookup"><span data-stu-id="00c0c-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-164">int</span><span class="sxs-lookup"><span data-stu-id="00c0c-164">int</span></span></p></td>
<td><p><span data-ttu-id="00c0c-165">Der Typ des Konferenzservers.</span><span class="sxs-lookup"><span data-stu-id="00c0c-165">Type of conference server.</span></span> <span data-ttu-id="00c0c-166">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="00c0c-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-169">Konferenzserver Kategorie.</span><span class="sxs-lookup"><span data-stu-id="00c0c-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-172">Die Version des Clients, die von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-174">int</span><span class="sxs-lookup"><span data-stu-id="00c0c-174">int</span></span></p></td>
<td><p><span data-ttu-id="00c0c-175">Der Client, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="00c0c-176">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="00c0c-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-179">Der Name der Kategorie des Clients, der von dem Benutzer verwendet wurde, der Teil der Sitzung war.</span><span class="sxs-lookup"><span data-stu-id="00c0c-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="00c0c-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-182">Der URI des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="00c0c-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-185">Der Typ des URIs des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="00c0c-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="00c0c-186">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-189">Der Mandant des Benutzers, dessen Namen für die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="00c0c-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="00c0c-190">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="00c0c-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-193">Der URI des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-196">Der Typ des URIs des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="00c0c-197">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-200">Der Mandant des Benutzers, der die Sitzung angewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="00c0c-201">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-202"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="00c0c-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-204">SIP-Dialogfeld-ID.</span><span class="sxs-lookup"><span data-stu-id="00c0c-204">SIP dialog ID.</span></span> <span data-ttu-id="00c0c-205">Das Format ist</span><span class="sxs-lookup"><span data-stu-id="00c0c-205">The format is</span></span></p>
<p><span data-ttu-id="00c0c-206">:d ialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="00c0c-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-208">datetime</span><span class="sxs-lookup"><span data-stu-id="00c0c-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="00c0c-209">Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="00c0c-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="00c0c-210">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-212">int</span><span class="sxs-lookup"><span data-stu-id="00c0c-212">int</span></span></p></td>
<td><p><span data-ttu-id="00c0c-213">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00c0c-213">ID number to identify the session.</span></span> <span data-ttu-id="00c0c-214">Wird in Verbindung mit ReplaceDialogIdTime verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00c0c-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="00c0c-215">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="00c0c-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="00c0c-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-218">SIP-Dialog-ID, die die Sitzung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="00c0c-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="00c0c-219">Das Format des is:</span><span class="sxs-lookup"><span data-stu-id="00c0c-219">The format of the is:</span></span></p>
<p><span data-ttu-id="00c0c-220">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="00c0c-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-222">bit</span><span class="sxs-lookup"><span data-stu-id="00c0c-222">bit</span></span></p></td>
<td><p><span data-ttu-id="00c0c-223">Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="00c0c-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-225">bit</span><span class="sxs-lookup"><span data-stu-id="00c0c-225">bit</span></span></p></td>
<td><p><span data-ttu-id="00c0c-226">Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="00c0c-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-228">bit</span><span class="sxs-lookup"><span data-stu-id="00c0c-228">bit</span></span></p></td>
<td><p><span data-ttu-id="00c0c-229">Gibt an, ob sich der Benutzer vom internen Netzwerk anmeldet.</span><span class="sxs-lookup"><span data-stu-id="00c0c-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-230"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-231">datetime</span><span class="sxs-lookup"><span data-stu-id="00c0c-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="00c0c-232">Zeitpunkt der Antwort auf die erste Einladungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="00c0c-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="00c0c-233">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="00c0c-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="00c0c-234">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="00c0c-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-235"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-236">int</span><span class="sxs-lookup"><span data-stu-id="00c0c-236">int</span></span></p></td>
<td><p><span data-ttu-id="00c0c-237">SIP-Antwortcode für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="00c0c-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="00c0c-238">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="00c0c-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="00c0c-239">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="00c0c-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-240"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-241">int</span><span class="sxs-lookup"><span data-stu-id="00c0c-241">int</span></span></p></td>
<td><p><span data-ttu-id="00c0c-242">Diagnose-ID, die aus Sitzungs-SIP-Headern erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="00c0c-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-245">Inhaltstyp für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="00c0c-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-248">FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-251">Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="00c0c-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-254">Vermittlungs Server, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-257">Gateway, das vom Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00c0c-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00c0c-260">Der FQDN des Edge-Servers, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c0c-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-262">smallint</span><span class="sxs-lookup"><span data-stu-id="00c0c-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="00c0c-263">Gibt die Attribute des Benutzers an, der an der Sitzung teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="00c0c-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="00c0c-264">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="00c0c-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="00c0c-265">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="00c0c-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c0c-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="00c0c-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="00c0c-267">smallint</span><span class="sxs-lookup"><span data-stu-id="00c0c-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="00c0c-268">Gibt die anrufattribute an.</span><span class="sxs-lookup"><span data-stu-id="00c0c-268">Indicates the call attributes.</span></span> <span data-ttu-id="00c0c-269">Die folgenden Attributdefinitionen sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="00c0c-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="00c0c-270">0x01 – wiederholte Session0</span><span class="sxs-lookup"><span data-stu-id="00c0c-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="00c0c-271">x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="00c0c-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

