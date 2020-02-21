---
title: 'Lync Server 2013: tblComplianceData'
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
ms.openlocfilehash: f159a71469335cfb2af1401e8693802b3c8d1870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="a7e0d-102">tblComplianceData in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e0d-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7e0d-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a7e0d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a7e0d-104">"tblComplianceData" enthält die Kompatibilitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="a7e0d-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="a7e0d-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="a7e0d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7e0d-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="a7e0d-106">Column</span></span></th>
<th><span data-ttu-id="a7e0d-107">Typ</span><span class="sxs-lookup"><span data-stu-id="a7e0d-107">Type</span></span></th>
<th><span data-ttu-id="a7e0d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7e0d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7e0d-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a7e0d-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-110">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a7e0d-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-111">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a7e0d-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e0d-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="a7e0d-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-113">smalldatetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a7e0d-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-114">Zeitpunkt des Einfügevorgangs (kann für "cmplType=9" in ferner Zukunft liegen, da der Eintrag in diesem Fall nur ein Platzhalter ist).</span><span class="sxs-lookup"><span data-stu-id="a7e0d-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e0d-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="a7e0d-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a7e0d-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-117">Typ des Kompatibilitätsereignisses:</span><span class="sxs-lookup"><span data-stu-id="a7e0d-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7e0d-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="a7e0d-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="a7e0d-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="a7e0d-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="a7e0d-120">3: Dateidownload</span><span class="sxs-lookup"><span data-stu-id="a7e0d-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="a7e0d-121">4: Dateiupload</span><span class="sxs-lookup"><span data-stu-id="a7e0d-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="a7e0d-122">9: Vorläufige Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="a7e0d-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="a7e0d-123">10: Chatlöschung (mit Ersatz)</span><span class="sxs-lookup"><span data-stu-id="a7e0d-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="a7e0d-124">11: Chatbereinigung</span><span class="sxs-lookup"><span data-stu-id="a7e0d-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e0d-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="a7e0d-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-126">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a7e0d-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-127">Zeitstempel für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a7e0d-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e0d-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="a7e0d-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-129">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a7e0d-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-130">Kanal-URI (Uniform Resource Identifier)</span><span class="sxs-lookup"><span data-stu-id="a7e0d-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e0d-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="a7e0d-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-132">bigint</span><span class="sxs-lookup"><span data-stu-id="a7e0d-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-133">Chat-ID (entsprechend der Tabelle "tblChat.chatId").</span><span class="sxs-lookup"><span data-stu-id="a7e0d-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e0d-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="a7e0d-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-135">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a7e0d-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-136">Prinzipal-ID des Bereitstellers (entsprechend der Tabelle "tblPrincipal.prinID").</span><span class="sxs-lookup"><span data-stu-id="a7e0d-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7e0d-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="a7e0d-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-138">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a7e0d-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-139">Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="a7e0d-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7e0d-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="a7e0d-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a7e0d-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-142">Nachricht (Codierung abhängig von "cmplType").</span><span class="sxs-lookup"><span data-stu-id="a7e0d-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a7e0d-143">Key</span><span class="sxs-lookup"><span data-stu-id="a7e0d-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7e0d-144">Spalte</span><span class="sxs-lookup"><span data-stu-id="a7e0d-144">Column</span></span></th>
<th><span data-ttu-id="a7e0d-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7e0d-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7e0d-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a7e0d-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="a7e0d-147">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="a7e0d-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

