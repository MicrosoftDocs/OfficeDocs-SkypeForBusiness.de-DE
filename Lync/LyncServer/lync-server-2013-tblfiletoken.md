---
title: 'Lync Server 2013: tblFileToken'
description: 'Lync Server 2013: tblFileToken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547631"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="b56f1-103">tblFileToken in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b56f1-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b56f1-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b56f1-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b56f1-105">TblFileToken enthält temporäre Token für die Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="b56f1-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="b56f1-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="b56f1-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b56f1-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="b56f1-107">Column</span></span></th>
<th><span data-ttu-id="b56f1-108">Typ</span><span class="sxs-lookup"><span data-stu-id="b56f1-108">Type</span></span></th>
<th><span data-ttu-id="b56f1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b56f1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b56f1-110">FileToken</span><span class="sxs-lookup"><span data-stu-id="b56f1-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="b56f1-111">nvarchar (50), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b56f1-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="b56f1-112">Eindeutiges Token (eine GUID).</span><span class="sxs-lookup"><span data-stu-id="b56f1-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b56f1-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="b56f1-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="b56f1-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b56f1-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b56f1-115">ID des Prinzipals, der die Datei überträgt.</span><span class="sxs-lookup"><span data-stu-id="b56f1-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b56f1-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="b56f1-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="b56f1-117">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b56f1-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="b56f1-118">GUID des Chatroomknotens.</span><span class="sxs-lookup"><span data-stu-id="b56f1-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b56f1-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="b56f1-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="b56f1-120">datetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b56f1-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="b56f1-p101">Ablaufzeit. (Token laufen nach 30 Minuten ab, wenn sie nicht gebunden werden (siehe Beschreibungen in dieser Tabelle.)</span><span class="sxs-lookup"><span data-stu-id="b56f1-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b56f1-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="b56f1-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="b56f1-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b56f1-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b56f1-125">URL der übertragenen Datei (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="b56f1-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b56f1-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="b56f1-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="b56f1-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b56f1-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b56f1-128">URL des Miniaturbilds der übertragenen Datei (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="b56f1-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b56f1-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="b56f1-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="b56f1-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="b56f1-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="b56f1-131">Zeitstempel für die tatsächliche Dateiübertragung (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="b56f1-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b56f1-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="b56f1-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="b56f1-133">Bit</span><span class="sxs-lookup"><span data-stu-id="b56f1-133">bit</span></span></p></td>
<td><p><span data-ttu-id="b56f1-134">True bei Upload; False bei Download (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="b56f1-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b56f1-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="b56f1-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="b56f1-136">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b56f1-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b56f1-p102">True, wenn das Token gebunden ist. Wird verwendet, um das Token in der Tabelle zu behalten, bis die relevanten Felder vom Kompatibilitätsdienst abgerufen werden konnten.</span><span class="sxs-lookup"><span data-stu-id="b56f1-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b56f1-139">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b56f1-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b56f1-140">Spalte</span><span class="sxs-lookup"><span data-stu-id="b56f1-140">Column</span></span></th>
<th><span data-ttu-id="b56f1-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b56f1-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b56f1-142">FileToken</span><span class="sxs-lookup"><span data-stu-id="b56f1-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="b56f1-143">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="b56f1-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b56f1-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="b56f1-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="b56f1-145">Fremdschlüssel mit Abfrage der tblNode.nodeGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b56f1-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

