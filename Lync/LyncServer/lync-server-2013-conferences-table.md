---
title: 'Lync Server 2013: Conferences-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="87491-102">Conferences-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87491-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87491-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="87491-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="87491-104">Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.</span><span class="sxs-lookup"><span data-stu-id="87491-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87491-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="87491-105">Column</span></span></th>
<th><span data-ttu-id="87491-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="87491-106">Data Type</span></span></th>
<th><span data-ttu-id="87491-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="87491-107">Key/Index</span></span></th>
<th><span data-ttu-id="87491-108">Details</span><span class="sxs-lookup"><span data-stu-id="87491-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87491-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="87491-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-110">datetime</span><span class="sxs-lookup"><span data-stu-id="87491-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="87491-111">Primary</span><span class="sxs-lookup"><span data-stu-id="87491-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="87491-112">Uhrzeit, zu der die Konferenzanforderung vom CdR-Agenten erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="87491-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="87491-113">Wird nur als Primärschlüssel verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="87491-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87491-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="87491-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-115">int</span><span class="sxs-lookup"><span data-stu-id="87491-115">int</span></span></p></td>
<td><p><span data-ttu-id="87491-116">Primary</span><span class="sxs-lookup"><span data-stu-id="87491-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="87491-117">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="87491-117">ID number to identify the session.</span></span> <span data-ttu-id="87491-118">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="87491-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87491-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="87491-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-120">int</span><span class="sxs-lookup"><span data-stu-id="87491-120">int</span></span></p></td>
<td><p><span data-ttu-id="87491-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="87491-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87491-122">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="87491-122">Conference URI.</span></span> <span data-ttu-id="87491-123">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="87491-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87491-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="87491-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="87491-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="87491-126">Nützlich für wiederkehrende Konferenzen; jede Instanz einer Besprechungsserie hat dieselbe <strong>ConferenceUri</strong>, hat aber eine andere <strong>ConfInstance</strong>.</span><span class="sxs-lookup"><span data-stu-id="87491-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87491-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="87491-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-128">datetime</span><span class="sxs-lookup"><span data-stu-id="87491-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="87491-129">Startzeit der Konferenz</span><span class="sxs-lookup"><span data-stu-id="87491-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87491-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="87491-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-131">datetime</span><span class="sxs-lookup"><span data-stu-id="87491-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="87491-132">Startzeit der Konferenz</span><span class="sxs-lookup"><span data-stu-id="87491-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87491-133"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="87491-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-134">int</span><span class="sxs-lookup"><span data-stu-id="87491-134">int</span></span></p></td>
<td><p><span data-ttu-id="87491-135">Fremd</span><span class="sxs-lookup"><span data-stu-id="87491-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87491-136">Die ID-Nummer zur Identifizierung des Pools, in dem die Konferenz aufgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="87491-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="87491-137">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="87491-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87491-138"><strong>Organizer-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="87491-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-139">Int</span><span class="sxs-lookup"><span data-stu-id="87491-139">Int</span></span></p></td>
<td><p><span data-ttu-id="87491-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="87491-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87491-141">Die ID-Nummer zum Identifizieren des Organisator-URIs dieser Konferenz.</span><span class="sxs-lookup"><span data-stu-id="87491-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="87491-142">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="87491-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87491-143"><strong>Kennzeichnen</strong></span><span class="sxs-lookup"><span data-stu-id="87491-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-144">smallint</span><span class="sxs-lookup"><span data-stu-id="87491-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87491-145">Eine Bitmaske, die Konferenz Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="87491-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="87491-146">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="87491-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="87491-147">0X01</span><span class="sxs-lookup"><span data-stu-id="87491-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="87491-148">Synthetischen</span><span class="sxs-lookup"><span data-stu-id="87491-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="87491-149">Transaktion</span><span class="sxs-lookup"><span data-stu-id="87491-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87491-150"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="87491-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="87491-151">bit</span><span class="sxs-lookup"><span data-stu-id="87491-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87491-152">Internes Feld, das vom Überwachungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87491-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="87491-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="87491-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87491-154">\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1.</span><span class="sxs-lookup"><span data-stu-id="87491-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="87491-155">Wenn zwei Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, und für den anderen wird 2 usw.</span><span class="sxs-lookup"><span data-stu-id="87491-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

