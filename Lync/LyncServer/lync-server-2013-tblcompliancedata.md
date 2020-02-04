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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="bc410-102">tblComplianceData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc410-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc410-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bc410-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bc410-104">tblComplianceData enthält die Konformitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="bc410-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="bc410-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="bc410-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc410-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="bc410-106">Column</span></span></th>
<th><span data-ttu-id="bc410-107">Typ</span><span class="sxs-lookup"><span data-stu-id="bc410-107">Type</span></span></th>
<th><span data-ttu-id="bc410-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc410-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc410-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="bc410-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="bc410-110">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bc410-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bc410-111">Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="bc410-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc410-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="bc410-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="bc410-113">smalldatetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bc410-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bc410-114">Zeitpunkt der Einfügung (kann für cmplType = 9 weit in der Zukunft liegen, da der Eintrag nur ein Platzhalter in diesem Fall ist).</span><span class="sxs-lookup"><span data-stu-id="bc410-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc410-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="bc410-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="bc410-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bc410-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bc410-117">Art des Konformitäts Ereignisses:</span><span class="sxs-lookup"><span data-stu-id="bc410-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc410-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="bc410-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="bc410-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="bc410-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="bc410-120">3: Herunterladen von Dateien</span><span class="sxs-lookup"><span data-stu-id="bc410-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="bc410-121">4: Hochladen von Dateien</span><span class="sxs-lookup"><span data-stu-id="bc410-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="bc410-122">9: provisorische Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="bc410-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="bc410-123">10: Löschen des Chats (mit Replace)</span><span class="sxs-lookup"><span data-stu-id="bc410-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="bc410-124">11: Chat-Bereinigung</span><span class="sxs-lookup"><span data-stu-id="bc410-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc410-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="bc410-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="bc410-126">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bc410-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bc410-127">Zeitstempel für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bc410-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc410-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="bc410-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="bc410-129">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bc410-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="bc410-130">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="bc410-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc410-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="bc410-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="bc410-132">bigint</span><span class="sxs-lookup"><span data-stu-id="bc410-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="bc410-133">Chat-ID (entsprechend der tblChat. Chat-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="bc410-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc410-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="bc410-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="bc410-135">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bc410-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bc410-136">Prinzipal-ID des Plakats (entsprechend der tblPrincipal. prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="bc410-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc410-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="bc410-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="bc410-138">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bc410-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="bc410-139">Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="bc410-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc410-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="bc410-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="bc410-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="bc410-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="bc410-142">Nachricht (Codierung hängt von cmplType ab).</span><span class="sxs-lookup"><span data-stu-id="bc410-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bc410-143">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="bc410-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc410-144">Spalte</span><span class="sxs-lookup"><span data-stu-id="bc410-144">Column</span></span></th>
<th><span data-ttu-id="bc410-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc410-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc410-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="bc410-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="bc410-147">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="bc410-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

