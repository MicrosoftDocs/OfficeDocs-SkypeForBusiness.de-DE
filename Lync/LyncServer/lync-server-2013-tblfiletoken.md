---
title: 'Lync Server 2013: tblFileToken'
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
ms.openlocfilehash: 47531c91ec7fed7e758bd73285f4e995afa65941
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509332"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="7dc03-102">tblFileToken in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dc03-102">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dc03-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7dc03-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7dc03-104">TblFileToken enthält temporäre Token für die Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="7dc03-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="7dc03-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="7dc03-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dc03-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="7dc03-106">Column</span></span></th>
<th><span data-ttu-id="7dc03-107">Typ</span><span class="sxs-lookup"><span data-stu-id="7dc03-107">Type</span></span></th>
<th><span data-ttu-id="7dc03-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dc03-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dc03-109">FileToken</span><span class="sxs-lookup"><span data-stu-id="7dc03-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="7dc03-110">nvarchar (50), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7dc03-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="7dc03-111">Eindeutiges Token (eine GUID).</span><span class="sxs-lookup"><span data-stu-id="7dc03-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc03-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="7dc03-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="7dc03-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7dc03-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7dc03-114">ID des Prinzipals, der die Datei überträgt.</span><span class="sxs-lookup"><span data-stu-id="7dc03-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc03-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="7dc03-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="7dc03-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7dc03-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7dc03-117">GUID des Chatroomknotens.</span><span class="sxs-lookup"><span data-stu-id="7dc03-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc03-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="7dc03-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="7dc03-119">datetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7dc03-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="7dc03-p101">Ablaufzeit. (Token laufen nach 30 Minuten ab, wenn sie nicht gebunden werden (siehe Beschreibungen in dieser Tabelle.)</span><span class="sxs-lookup"><span data-stu-id="7dc03-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc03-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="7dc03-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="7dc03-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dc03-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dc03-124">URL der übertragenen Datei (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="7dc03-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc03-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="7dc03-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="7dc03-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dc03-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dc03-127">URL des Miniaturbilds der übertragenen Datei (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="7dc03-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc03-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="7dc03-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="7dc03-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="7dc03-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="7dc03-130">Zeitstempel für die tatsächliche Dateiübertragung (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="7dc03-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc03-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="7dc03-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="7dc03-132">Bit</span><span class="sxs-lookup"><span data-stu-id="7dc03-132">bit</span></span></p></td>
<td><p><span data-ttu-id="7dc03-133">True bei Upload; False bei Download (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="7dc03-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc03-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="7dc03-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="7dc03-135">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7dc03-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7dc03-p102">True, wenn das Token gebunden ist. Wird verwendet, um das Token in der Tabelle zu behalten, bis die relevanten Felder vom Kompatibilitätsdienst abgerufen werden konnten.</span><span class="sxs-lookup"><span data-stu-id="7dc03-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7dc03-138">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="7dc03-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dc03-139">Spalte</span><span class="sxs-lookup"><span data-stu-id="7dc03-139">Column</span></span></th>
<th><span data-ttu-id="7dc03-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dc03-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dc03-141">FileToken</span><span class="sxs-lookup"><span data-stu-id="7dc03-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="7dc03-142">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="7dc03-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc03-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="7dc03-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="7dc03-144">Fremdschlüssel mit Abfrage der tblNode.nodeGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7dc03-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

