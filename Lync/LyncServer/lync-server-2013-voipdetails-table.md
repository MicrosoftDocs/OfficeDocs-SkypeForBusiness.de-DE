---
title: 'Lync Server 2013: VoipDetails-Tabelle'
description: 'Lync Server 2013: VoipDetails-Tabelle.'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566281"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="4851c-103">VoipDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4851c-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4851c-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4851c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4851c-105">Jeder Datensatz steht für einen Anruf mit zwei Teilnehmern, wovon  mindestens einer ein VoIP-Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="4851c-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4851c-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="4851c-106">Column</span></span></th>
<th><span data-ttu-id="4851c-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4851c-107">Data Type</span></span></th>
<th><span data-ttu-id="4851c-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="4851c-108">Key/Index</span></span></th>
<th><span data-ttu-id="4851c-109">Details</span><span class="sxs-lookup"><span data-stu-id="4851c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4851c-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4851c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4851c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4851c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4851c-113">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="4851c-113">Time of session request.</span></span> <span data-ttu-id="4851c-114">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4851c-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4851c-115">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4851c-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-117">int</span><span class="sxs-lookup"><span data-stu-id="4851c-117">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-118">Primary</span><span class="sxs-lookup"><span data-stu-id="4851c-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="4851c-119">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4851c-119">ID number to identify the session.</span></span> <span data-ttu-id="4851c-120">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4851c-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4851c-121">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4851c-122"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-123">int</span><span class="sxs-lookup"><span data-stu-id="4851c-123">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-124">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-125"><strong>PhoneId</strong> des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="4851c-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="4851c-126">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4851c-127">Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufer um einen PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4851c-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4851c-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-129">int</span><span class="sxs-lookup"><span data-stu-id="4851c-129">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-130">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-131"><strong>PhoneId</strong> des Anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="4851c-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="4851c-132">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4851c-133">Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufempfänger um einen PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4851c-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4851c-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-135">int</span><span class="sxs-lookup"><span data-stu-id="4851c-135">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-136">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-137">Der Vermittlungsserver, von dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="4851c-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="4851c-138">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4851c-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-140">int</span><span class="sxs-lookup"><span data-stu-id="4851c-140">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-141">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-142">Der Vermittlungsserver, an den der Anruf geht.</span><span class="sxs-lookup"><span data-stu-id="4851c-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="4851c-143">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4851c-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-145">int</span><span class="sxs-lookup"><span data-stu-id="4851c-145">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-146">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-147">Das Gateway, von dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="4851c-147">Gateway the call is coming from.</span></span> <span data-ttu-id="4851c-148">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4851c-149"><strong>Togateways</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-150">int</span><span class="sxs-lookup"><span data-stu-id="4851c-150">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-151">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-152">Das Gateway, an das der Anruf geht.</span><span class="sxs-lookup"><span data-stu-id="4851c-152">Gateway the call is going to.</span></span> <span data-ttu-id="4851c-153">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4851c-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-155">int</span><span class="sxs-lookup"><span data-stu-id="4851c-155">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-156">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-157">URI des Benutzers, der den Anruf unterbrochen hat, sofern der Benutzer über einen URI verfügt.</span><span class="sxs-lookup"><span data-stu-id="4851c-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="4851c-158">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4851c-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="4851c-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="4851c-160">int</span><span class="sxs-lookup"><span data-stu-id="4851c-160">int</span></span></p></td>
<td><p><span data-ttu-id="4851c-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="4851c-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4851c-162">ID des Telefons, das den Anruf unterbrochen hat, sofern der Anruf von einem Telefon unterbrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="4851c-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="4851c-163">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4851c-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

