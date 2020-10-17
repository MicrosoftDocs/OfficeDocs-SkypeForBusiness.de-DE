---
title: 'Lync Server 2013: Ansicht "Konferenzen"'
description: 'Lync Server 2013: Ansicht "Konferenzen".'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561581"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="645ea-103">Ansicht "Konferenzen" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="645ea-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="645ea-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="645ea-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="645ea-105">Die Konferenzansicht enthält Informationen zu den Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="645ea-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="645ea-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="645ea-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="645ea-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="645ea-107">Column</span></span></th>
<th><span data-ttu-id="645ea-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="645ea-108">Data Type</span></span></th>
<th><span data-ttu-id="645ea-109">Details</span><span class="sxs-lookup"><span data-stu-id="645ea-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="645ea-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="645ea-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="645ea-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="645ea-112">Time of session request.</span></span> <span data-ttu-id="645ea-113">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="645ea-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="645ea-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="645ea-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="645ea-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-116">int</span><span class="sxs-lookup"><span data-stu-id="645ea-116">int</span></span></p></td>
<td><p><span data-ttu-id="645ea-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="645ea-117">ID number to identify the session.</span></span> <span data-ttu-id="645ea-118">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="645ea-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="645ea-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="645ea-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="645ea-120"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="645ea-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="645ea-122">Der URI für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="645ea-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="645ea-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="645ea-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="645ea-125">Der Typ des Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="645ea-125">Type of the conference URI.</span></span> <span data-ttu-id="645ea-126">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="645ea-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="645ea-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-128">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="645ea-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="645ea-p105">Wird für wiederkehrende Konferenzen verwendet. Jede Instanz einer wiederkehrenden Konferenz hat die gleiche ConferenceUri, aber eine andere ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="645ea-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="645ea-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-132">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="645ea-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="645ea-133">Die Startzeit für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="645ea-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="645ea-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-135">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="645ea-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="645ea-136">Die Endzeit für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="645ea-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="645ea-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="645ea-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="645ea-139">Der URI des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="645ea-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="645ea-140"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="645ea-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="645ea-142">Der URI-Typ des Benutzers, der die Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="645ea-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="645ea-143">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="645ea-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="645ea-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="645ea-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="645ea-146">Der Mandant des Benutzers, der die Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="645ea-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="645ea-147">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="645ea-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="645ea-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="645ea-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="645ea-150">Der vollqualifizierte Domänenname des Pools, von dem die Konferenz gehostet wurde.</span><span class="sxs-lookup"><span data-stu-id="645ea-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="645ea-151"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="645ea-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="645ea-152">smallint</span><span class="sxs-lookup"><span data-stu-id="645ea-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="645ea-p108">Eine Bitmaske, die Konferenzattribute enthält. Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="645ea-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="645ea-155">0X01 – Synthetische Transaktion</span><span class="sxs-lookup"><span data-stu-id="645ea-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

