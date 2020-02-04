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
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="5e389-102">VoipDetails-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e389-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e389-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5e389-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5e389-104">Jeder Datensatz steht für 1 2-Party-Anrufe, bei denen mindestens ein Nutzer ein VoIP-Nutzer ist.</span><span class="sxs-lookup"><span data-stu-id="5e389-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e389-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="5e389-105">Column</span></span></th>
<th><span data-ttu-id="5e389-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5e389-106">Data Type</span></span></th>
<th><span data-ttu-id="5e389-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="5e389-107">Key/Index</span></span></th>
<th><span data-ttu-id="5e389-108">Details</span><span class="sxs-lookup"><span data-stu-id="5e389-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e389-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-110">datetime</span><span class="sxs-lookup"><span data-stu-id="5e389-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e389-111">Primary</span><span class="sxs-lookup"><span data-stu-id="5e389-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="5e389-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="5e389-112">Time of session request.</span></span> <span data-ttu-id="5e389-113">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5e389-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="5e389-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e389-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-116">int</span><span class="sxs-lookup"><span data-stu-id="5e389-116">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5e389-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="5e389-118">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5e389-118">ID number to identify the session.</span></span> <span data-ttu-id="5e389-119">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5e389-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="5e389-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e389-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-122">int</span><span class="sxs-lookup"><span data-stu-id="5e389-122">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-124"><strong>Telefonnummer</strong> des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="5e389-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="5e389-125">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5e389-126">Wenn nicht NULL und <strong>FromGatewayId</strong> nicht NULL ist, war der Aufrufer ein PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5e389-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e389-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-128">int</span><span class="sxs-lookup"><span data-stu-id="5e389-128">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-129">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-130"><strong>Telefonnummer</strong> des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="5e389-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="5e389-131">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5e389-132">Wenn nicht NULL und <strong>togateway</strong> -Nr NULL ist, war der Anrufempfänger ein PSTN-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5e389-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e389-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-134">int</span><span class="sxs-lookup"><span data-stu-id="5e389-134">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-135">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-136">Der Vermittlungs Server, aus dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="5e389-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="5e389-137">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e389-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-139">int</span><span class="sxs-lookup"><span data-stu-id="5e389-139">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-141">Der Vermittlungs Server wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5e389-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="5e389-142">Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e389-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-144">int</span><span class="sxs-lookup"><span data-stu-id="5e389-144">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-145">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-146">Gateway, aus dem der Anruf kommt.</span><span class="sxs-lookup"><span data-stu-id="5e389-146">Gateway the call is coming from.</span></span> <span data-ttu-id="5e389-147">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e389-148"><strong>Togatewayservernummer</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-149">int</span><span class="sxs-lookup"><span data-stu-id="5e389-149">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-150">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-151">Gateway, an das der Anruf geht.</span><span class="sxs-lookup"><span data-stu-id="5e389-151">Gateway the call is going to.</span></span> <span data-ttu-id="5e389-152">Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e389-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-154">int</span><span class="sxs-lookup"><span data-stu-id="5e389-154">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-155">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-156">Der URI des Benutzers, der den Anruf getrennt hat, wenn der Benutzer über einen URI verfügt.</span><span class="sxs-lookup"><span data-stu-id="5e389-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="5e389-157">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e389-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="5e389-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e389-159">int</span><span class="sxs-lookup"><span data-stu-id="5e389-159">int</span></span></p></td>
<td><p><span data-ttu-id="5e389-160">Fremd</span><span class="sxs-lookup"><span data-stu-id="5e389-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e389-161">Die ID des Telefons, das den Anruf getrennt hat, wurde von einem Telefon getrennt.</span><span class="sxs-lookup"><span data-stu-id="5e389-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="5e389-162">Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5e389-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

