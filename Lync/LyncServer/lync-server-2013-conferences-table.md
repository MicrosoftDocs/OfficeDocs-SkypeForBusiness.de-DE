---
title: 'Lync Server 2013: Tabelle "Konferenzen"'
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
ms.openlocfilehash: 218879c8e2c64178fc140d46199529f86ec7dc31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="3f6d9-102">Konferenz Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f6d9-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f6d9-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3f6d9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3f6d9-104">Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f6d9-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="3f6d9-105">Column</span></span></th>
<th><span data-ttu-id="3f6d9-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3f6d9-106">Data Type</span></span></th>
<th><span data-ttu-id="3f6d9-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="3f6d9-107">Key/Index</span></span></th>
<th><span data-ttu-id="3f6d9-108">Details</span><span class="sxs-lookup"><span data-stu-id="3f6d9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f6d9-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3f6d9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="3f6d9-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-112">Zeitpunkt, zu dem die Konferenzanforderung vom KDS-Agent erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="3f6d9-113">Wird nur als Primärschlüssel verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6d9-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-115">int</span><span class="sxs-lookup"><span data-stu-id="3f6d9-115">int</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-116">Primary</span><span class="sxs-lookup"><span data-stu-id="3f6d9-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-117">ID number to identify the session.</span></span> <span data-ttu-id="3f6d9-118">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6d9-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-120">int</span><span class="sxs-lookup"><span data-stu-id="3f6d9-120">int</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="3f6d9-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-122">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="3f6d9-122">Conference URI.</span></span> <span data-ttu-id="3f6d9-123">Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6d9-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6d9-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="3f6d9-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3f6d9-126">Nützlich für wiederkehrende Konferenzen; jede Instanz einer wiederkehrenden Konferenz hat dieselbe <strong>ConferenceUri</strong>, jedoch eine andere <strong>ConfInstance</strong>.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6d9-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-128">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3f6d9-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3f6d9-129">Startzeit der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6d9-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-131">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3f6d9-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3f6d9-132">Startzeit der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6d9-133"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-134">int</span><span class="sxs-lookup"><span data-stu-id="3f6d9-134">int</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-135">Fremd</span><span class="sxs-lookup"><span data-stu-id="3f6d9-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-136">ID-Nummer zum Identifizieren des Pools, in dem die Konferenz erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="3f6d9-137">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6d9-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6d9-138"><strong>Organizer-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-139">Int</span><span class="sxs-lookup"><span data-stu-id="3f6d9-139">Int</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-140">Fremd</span><span class="sxs-lookup"><span data-stu-id="3f6d9-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6d9-141">ID-Nummer zum Identifizieren des Organisator-URI dieser Konferenz.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="3f6d9-142">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6d9-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6d9-143"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-144">smallint</span><span class="sxs-lookup"><span data-stu-id="3f6d9-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6d9-145">Eine Bitmaske, die Konferenz Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="3f6d9-146">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="3f6d9-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f6d9-147">0X01</span><span class="sxs-lookup"><span data-stu-id="3f6d9-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="3f6d9-148">Synthetischen</span><span class="sxs-lookup"><span data-stu-id="3f6d9-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="3f6d9-149">Transaktion</span><span class="sxs-lookup"><span data-stu-id="3f6d9-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6d9-150"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="3f6d9-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6d9-151">Bit</span><span class="sxs-lookup"><span data-stu-id="3f6d9-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6d9-152">Internes Feld, das vom Überwachungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="3f6d9-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3f6d9-154">\*Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="3f6d9-155">Wenn zwei Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, und für den anderen werden 2 usw.</span><span class="sxs-lookup"><span data-stu-id="3f6d9-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

