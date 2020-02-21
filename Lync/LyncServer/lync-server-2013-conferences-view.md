---
title: 'Lync Server 2013: Ansicht "Konferenzen"'
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
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="ae889-102">Ansicht "Konferenzen" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae889-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae889-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ae889-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ae889-104">Die Konferenzansicht enthält Informationen zu den Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="ae889-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="ae889-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ae889-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae889-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="ae889-106">Column</span></span></th>
<th><span data-ttu-id="ae889-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ae889-107">Data Type</span></span></th>
<th><span data-ttu-id="ae889-108">Details</span><span class="sxs-lookup"><span data-stu-id="ae889-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae889-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ae889-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae889-111">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="ae889-111">Time of session request.</span></span> <span data-ttu-id="ae889-112">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="ae889-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ae889-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ae889-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae889-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-115">int</span><span class="sxs-lookup"><span data-stu-id="ae889-115">int</span></span></p></td>
<td><p><span data-ttu-id="ae889-116">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ae889-116">ID number to identify the session.</span></span> <span data-ttu-id="ae889-117">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ae889-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ae889-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ae889-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae889-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ae889-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae889-121">Der URI für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="ae889-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae889-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ae889-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae889-124">Der Typ des Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="ae889-124">Type of the conference URI.</span></span> <span data-ttu-id="ae889-125">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ae889-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae889-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ae889-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ae889-p105">Wird für wiederkehrende Konferenzen verwendet. Jede Instanz einer wiederkehrenden Konferenz hat die gleiche ConferenceUri, aber eine andere ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="ae889-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae889-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-131">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ae889-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae889-132">Die Startzeit für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="ae889-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae889-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-134">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ae889-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae889-135">Die Endzeit für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="ae889-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae889-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ae889-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae889-138">Der URI des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="ae889-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae889-139"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ae889-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae889-141">Der URI-Typ des Benutzers, der die Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="ae889-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="ae889-142">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ae889-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae889-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ae889-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae889-145">Der Mandant des Benutzers, der die Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="ae889-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="ae889-146">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ae889-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae889-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ae889-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae889-149">Der vollqualifizierte Domänenname des Pools, von dem die Konferenz gehostet wurde.</span><span class="sxs-lookup"><span data-stu-id="ae889-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae889-150"><strong>Wert</strong></span><span class="sxs-lookup"><span data-stu-id="ae889-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ae889-151">smallint</span><span class="sxs-lookup"><span data-stu-id="ae889-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="ae889-p108">Eine Bitmaske, die Konferenzattribute enthält. Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ae889-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="ae889-154">0X01 – Synthetische Transaktion</span><span class="sxs-lookup"><span data-stu-id="ae889-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

