---
title: 'Lync Server 2013: Tabelle "Konferenzen"'
description: 'Lync Server 2013: Konferenz Tabelle.'
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
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561601"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="f7fa8-103">Konferenz Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7fa8-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7fa8-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f7fa8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f7fa8-105">Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7fa8-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="f7fa8-106">Column</span></span></th>
<th><span data-ttu-id="f7fa8-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f7fa8-107">Data Type</span></span></th>
<th><span data-ttu-id="f7fa8-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="f7fa8-108">Key/Index</span></span></th>
<th><span data-ttu-id="f7fa8-109">Details</span><span class="sxs-lookup"><span data-stu-id="f7fa8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7fa8-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f7fa8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f7fa8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-113">Zeitpunkt, zu dem die Konferenzanforderung vom KDS-Agent erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="f7fa8-114">Wird nur als Primärschlüssel verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7fa8-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-116">int</span><span class="sxs-lookup"><span data-stu-id="f7fa8-116">int</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-117">Primary</span><span class="sxs-lookup"><span data-stu-id="f7fa8-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-118">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-118">ID number to identify the session.</span></span> <span data-ttu-id="f7fa8-119">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7fa8-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-121">int</span><span class="sxs-lookup"><span data-stu-id="f7fa8-121">int</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="f7fa8-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-123">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="f7fa8-123">Conference URI.</span></span> <span data-ttu-id="f7fa8-124">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f7fa8-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7fa8-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-126">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f7fa8-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f7fa8-127">Nützlich für wiederkehrende Konferenzen; jede Instanz einer wiederkehrenden Konferenz hat dieselbe <strong>ConferenceUri</strong>, jedoch eine andere <strong>ConfInstance</strong>.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7fa8-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-129">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f7fa8-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f7fa8-130">Startzeit der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7fa8-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-132">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f7fa8-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f7fa8-133">Startzeit der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7fa8-134"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-135">int</span><span class="sxs-lookup"><span data-stu-id="f7fa8-135">int</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-136">Fremd</span><span class="sxs-lookup"><span data-stu-id="f7fa8-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-137">ID-Nummer zum Identifizieren des Pools, in dem die Konferenz erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="f7fa8-138">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f7fa8-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7fa8-139"><strong>Organizer-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-140">Int</span><span class="sxs-lookup"><span data-stu-id="f7fa8-140">Int</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-141">Fremd</span><span class="sxs-lookup"><span data-stu-id="f7fa8-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f7fa8-142">ID-Nummer zum Identifizieren des Organisator-URI dieser Konferenz.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="f7fa8-143">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f7fa8-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7fa8-144"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-145">smallint</span><span class="sxs-lookup"><span data-stu-id="f7fa8-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f7fa8-146">Eine Bitmaske, die Konferenz Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="f7fa8-147">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="f7fa8-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7fa8-148">0X01</span><span class="sxs-lookup"><span data-stu-id="f7fa8-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="f7fa8-149">Synthetischen</span><span class="sxs-lookup"><span data-stu-id="f7fa8-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="f7fa8-150">Transaction</span><span class="sxs-lookup"><span data-stu-id="f7fa8-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7fa8-151"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="f7fa8-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="f7fa8-152">Bit</span><span class="sxs-lookup"><span data-stu-id="f7fa8-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f7fa8-153">Internes Feld, das vom Überwachungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="f7fa8-154">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7fa8-155">\* Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="f7fa8-156">Wenn zwei Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, und für den anderen werden 2 usw.</span><span class="sxs-lookup"><span data-stu-id="f7fa8-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

