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
ms.openlocfilehash: d459262d5126dc6d55f930b20e54cbb1e69e04e9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="cbcc0-102">VoipDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbcc0-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbcc0-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cbcc0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cbcc0-104">Jeder Datensatz steht für einen Anruf mit zwei Teilnehmern, wovon  mindestens einer ein VoIP-Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbcc0-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="cbcc0-105">Column</span></span></th>
<th><span data-ttu-id="cbcc0-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="cbcc0-106">Data Type</span></span></th>
<th><span data-ttu-id="cbcc0-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="cbcc0-107">Key/Index</span></span></th>
<th><span data-ttu-id="cbcc0-108">Details</span><span class="sxs-lookup"><span data-stu-id="cbcc0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbcc0-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="cbcc0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-111">Primary</span><span class="sxs-lookup"><span data-stu-id="cbcc0-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-112">Time of session request.</span></span> <span data-ttu-id="cbcc0-113">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cbcc0-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbcc0-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-116">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-116">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-117">Primary</span><span class="sxs-lookup"><span data-stu-id="cbcc0-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-118">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-118">ID number to identify the session.</span></span> <span data-ttu-id="cbcc0-119">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cbcc0-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbcc0-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-122">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-122">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-124"><strong>PhoneId</strong> des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="cbcc0-125">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="cbcc0-126">Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufer um einen PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbcc0-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-128">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-128">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-129">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-130"><strong>PhoneId</strong> des Anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="cbcc0-131">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="cbcc0-132">Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufempfänger um einen PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbcc0-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-134">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-134">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-135">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-136">Der Vermittlungsserver, von dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="cbcc0-137">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbcc0-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-139">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-139">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-141">Der Vermittlungsserver, an den der Anruf geht.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="cbcc0-142">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbcc0-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-144">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-144">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-145">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-146">Das Gateway, von dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-146">Gateway the call is coming from.</span></span> <span data-ttu-id="cbcc0-147">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbcc0-148"><strong>Togateways</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-149">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-149">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-150">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-151">Das Gateway, an das der Anruf geht.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-151">Gateway the call is going to.</span></span> <span data-ttu-id="cbcc0-152">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbcc0-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-154">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-154">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-155">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-156">URI des Benutzers, der den Anruf unterbrochen hat, sofern der Benutzer über einen URI verfügt.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="cbcc0-157">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbcc0-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="cbcc0-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbcc0-159">int</span><span class="sxs-lookup"><span data-stu-id="cbcc0-159">int</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-160">Fremd</span><span class="sxs-lookup"><span data-stu-id="cbcc0-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbcc0-161">ID des Telefons, das den Anruf unterbrochen hat, sofern der Anruf von einem Telefon unterbrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="cbcc0-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="cbcc0-162">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcc0-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

