---
title: 'Lync Server 2013: VoipDetails-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26feac5b9995aa1a8444029442adcb9c935083d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535412"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="927f9-102">VoipDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="927f9-102">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="927f9-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="927f9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="927f9-104">Jeder Datensatz steht für einen Anruf mit zwei Teilnehmern, wovon  mindestens einer ein VoIP-Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="927f9-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="927f9-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="927f9-105">Column</span></span></th>
<th><span data-ttu-id="927f9-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="927f9-106">Data Type</span></span></th>
<th><span data-ttu-id="927f9-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="927f9-107">Key/Index</span></span></th>
<th><span data-ttu-id="927f9-108">Details</span><span class="sxs-lookup"><span data-stu-id="927f9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="927f9-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="927f9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="927f9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="927f9-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="927f9-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="927f9-112">Time of session request.</span></span> <span data-ttu-id="927f9-113">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="927f9-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="927f9-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="927f9-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-116">int</span><span class="sxs-lookup"><span data-stu-id="927f9-116">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-117">Primary</span><span class="sxs-lookup"><span data-stu-id="927f9-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="927f9-118">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="927f9-118">ID number to identify the session.</span></span> <span data-ttu-id="927f9-119">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="927f9-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="927f9-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="927f9-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-122">int</span><span class="sxs-lookup"><span data-stu-id="927f9-122">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-124"><strong>PhoneId</strong> des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="927f9-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="927f9-125">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="927f9-126">Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufer um einen PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="927f9-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="927f9-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-128">int</span><span class="sxs-lookup"><span data-stu-id="927f9-128">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-129">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-130"><strong>PhoneId</strong> des Anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="927f9-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="927f9-131">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="927f9-132">Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufempfänger um einen PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="927f9-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="927f9-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-134">int</span><span class="sxs-lookup"><span data-stu-id="927f9-134">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-135">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-136">Der Vermittlungsserver, von dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="927f9-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="927f9-137">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="927f9-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-139">int</span><span class="sxs-lookup"><span data-stu-id="927f9-139">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-141">Der Vermittlungsserver, an den der Anruf geht.</span><span class="sxs-lookup"><span data-stu-id="927f9-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="927f9-142">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="927f9-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-144">int</span><span class="sxs-lookup"><span data-stu-id="927f9-144">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-145">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-146">Das Gateway, von dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="927f9-146">Gateway the call is coming from.</span></span> <span data-ttu-id="927f9-147">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="927f9-148"><strong>Togateways</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-149">int</span><span class="sxs-lookup"><span data-stu-id="927f9-149">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-150">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-151">Das Gateway, an das der Anruf geht.</span><span class="sxs-lookup"><span data-stu-id="927f9-151">Gateway the call is going to.</span></span> <span data-ttu-id="927f9-152">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="927f9-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-154">int</span><span class="sxs-lookup"><span data-stu-id="927f9-154">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-155">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-156">URI des Benutzers, der den Anruf unterbrochen hat, sofern der Benutzer über einen URI verfügt.</span><span class="sxs-lookup"><span data-stu-id="927f9-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="927f9-157">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="927f9-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="927f9-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="927f9-159">int</span><span class="sxs-lookup"><span data-stu-id="927f9-159">int</span></span></p></td>
<td><p><span data-ttu-id="927f9-160">Fremd</span><span class="sxs-lookup"><span data-stu-id="927f9-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="927f9-161">ID des Telefons, das den Anruf unterbrochen hat, sofern der Anruf von einem Telefon unterbrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="927f9-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="927f9-162">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="927f9-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

