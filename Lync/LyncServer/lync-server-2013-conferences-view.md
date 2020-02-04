---
title: 'Lync Server 2013: Konferenz Ansicht'
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
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="9612c-102">Konferenz Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9612c-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9612c-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9612c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9612c-104">In der Ansicht "Konferenzen" werden Informationen zu den Konferenzen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9612c-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="9612c-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9612c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9612c-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="9612c-106">Column</span></span></th>
<th><span data-ttu-id="9612c-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9612c-107">Data Type</span></span></th>
<th><span data-ttu-id="9612c-108">Details</span><span class="sxs-lookup"><span data-stu-id="9612c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9612c-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9612c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9612c-111">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="9612c-111">Time of session request.</span></span> <span data-ttu-id="9612c-112">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9612c-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9612c-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9612c-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9612c-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-115">int</span><span class="sxs-lookup"><span data-stu-id="9612c-115">int</span></span></p></td>
<td><p><span data-ttu-id="9612c-116">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9612c-116">ID number to identify the session.</span></span> <span data-ttu-id="9612c-117">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9612c-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9612c-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9612c-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9612c-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9612c-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9612c-121">URI für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="9612c-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9612c-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9612c-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9612c-124">Der Typ des Konferenz-URIs.</span><span class="sxs-lookup"><span data-stu-id="9612c-124">Type of the conference URI.</span></span> <span data-ttu-id="9612c-125">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9612c-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9612c-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9612c-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9612c-128">Wird für wiederkehrende Konferenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9612c-128">Used for recurring conferences.</span></span> <span data-ttu-id="9612c-129">Jede Instanz einer Besprechungsserie hat dieselbe ConferenceUri, aber eine andere ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="9612c-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9612c-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-131">datetime</span><span class="sxs-lookup"><span data-stu-id="9612c-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="9612c-132">Startzeit für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="9612c-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9612c-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-134">datetime</span><span class="sxs-lookup"><span data-stu-id="9612c-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="9612c-135">Endzeit für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="9612c-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9612c-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9612c-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9612c-138">Der URI des Benutzers, der die Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="9612c-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9612c-139"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9612c-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9612c-141">Der Typ des URIs des Benutzers, der die Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="9612c-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="9612c-142">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9612c-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9612c-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9612c-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9612c-145">Der Mandant des Benutzers, der die Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="9612c-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="9612c-146">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9612c-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9612c-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9612c-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9612c-149">Vollständig qualifizierter Domänenname des Pools, in dem die Konferenz gehostet wurde.</span><span class="sxs-lookup"><span data-stu-id="9612c-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9612c-150"><strong>Kennzeichnen</strong></span><span class="sxs-lookup"><span data-stu-id="9612c-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="9612c-151">smallint</span><span class="sxs-lookup"><span data-stu-id="9612c-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="9612c-152">Bitmaske, die Konferenz Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="9612c-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="9612c-153">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="9612c-153">Possible values are:</span></span></p>
<p><span data-ttu-id="9612c-154">0X01 – synthetische Transaktion</span><span class="sxs-lookup"><span data-stu-id="9612c-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

