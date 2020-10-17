---
title: 'Lync Server 2013: tblComplianceData'
description: 'Lync Server 2013: tblComplianceData.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568101"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="2ab1f-103">tblComplianceData in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ab1f-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ab1f-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2ab1f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2ab1f-105">"tblComplianceData" enthält die Kompatibilitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="2ab1f-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="2ab1f-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="2ab1f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ab1f-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="2ab1f-107">Column</span></span></th>
<th><span data-ttu-id="2ab1f-108">Typ</span><span class="sxs-lookup"><span data-stu-id="2ab1f-108">Type</span></span></th>
<th><span data-ttu-id="2ab1f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ab1f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ab1f-110">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="2ab1f-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-111">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2ab1f-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-112">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2ab1f-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab1f-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="2ab1f-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-114">smalldatetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2ab1f-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-115">Zeitpunkt des Einfügevorgangs (kann für "cmplType=9" in ferner Zukunft liegen, da der Eintrag in diesem Fall nur ein Platzhalter ist).</span><span class="sxs-lookup"><span data-stu-id="2ab1f-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab1f-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="2ab1f-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2ab1f-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-118">Typ des Kompatibilitätsereignisses:</span><span class="sxs-lookup"><span data-stu-id="2ab1f-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ab1f-119">1: Chat</span><span class="sxs-lookup"><span data-stu-id="2ab1f-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="2ab1f-120">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="2ab1f-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="2ab1f-121">3: Dateidownload</span><span class="sxs-lookup"><span data-stu-id="2ab1f-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="2ab1f-122">4: Dateiupload</span><span class="sxs-lookup"><span data-stu-id="2ab1f-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="2ab1f-123">9: Vorläufige Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="2ab1f-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="2ab1f-124">10: Chatlöschung (mit Ersatz)</span><span class="sxs-lookup"><span data-stu-id="2ab1f-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="2ab1f-125">11: Chatbereinigung</span><span class="sxs-lookup"><span data-stu-id="2ab1f-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab1f-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="2ab1f-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-127">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2ab1f-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-128">Zeitstempel für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2ab1f-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab1f-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="2ab1f-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-130">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2ab1f-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-131">Kanal-URI (Uniform Resource Identifier)</span><span class="sxs-lookup"><span data-stu-id="2ab1f-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab1f-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="2ab1f-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-133">bigint</span><span class="sxs-lookup"><span data-stu-id="2ab1f-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-134">Chat-ID (entsprechend der Tabelle "tblChat.chatId").</span><span class="sxs-lookup"><span data-stu-id="2ab1f-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab1f-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="2ab1f-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-136">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2ab1f-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-137">Prinzipal-ID des Bereitstellers (entsprechend der Tabelle "tblPrincipal.prinID").</span><span class="sxs-lookup"><span data-stu-id="2ab1f-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab1f-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="2ab1f-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-139">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2ab1f-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-140">Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="2ab1f-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab1f-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="2ab1f-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-142">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2ab1f-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-143">Nachricht (Codierung abhängig von "cmplType").</span><span class="sxs-lookup"><span data-stu-id="2ab1f-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2ab1f-144">Key</span><span class="sxs-lookup"><span data-stu-id="2ab1f-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ab1f-145">Spalte</span><span class="sxs-lookup"><span data-stu-id="2ab1f-145">Column</span></span></th>
<th><span data-ttu-id="2ab1f-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ab1f-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ab1f-147">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="2ab1f-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="2ab1f-148">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="2ab1f-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

