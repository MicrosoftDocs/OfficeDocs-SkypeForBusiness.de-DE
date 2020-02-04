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
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="1f58f-102">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f58f-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f58f-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1f58f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1f58f-104">tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.</span><span class="sxs-lookup"><span data-stu-id="1f58f-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="1f58f-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="1f58f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f58f-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="1f58f-106">Column</span></span></th>
<th><span data-ttu-id="1f58f-107">Typ</span><span class="sxs-lookup"><span data-stu-id="1f58f-107">Type</span></span></th>
<th><span data-ttu-id="1f58f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f58f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f58f-109">FileToken</span><span class="sxs-lookup"><span data-stu-id="1f58f-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="1f58f-110">nvarchar (50); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1f58f-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="1f58f-111">Eindeutiges Token (eine GUID).</span><span class="sxs-lookup"><span data-stu-id="1f58f-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f58f-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="1f58f-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="1f58f-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1f58f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1f58f-114">Die ID des Prinzipals, der die Datei übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="1f58f-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f58f-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1f58f-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="1f58f-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1f58f-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1f58f-117">GUID des Chatroom-Knotens.</span><span class="sxs-lookup"><span data-stu-id="1f58f-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f58f-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="1f58f-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="1f58f-119">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1f58f-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="1f58f-120">Ablaufzeit.</span><span class="sxs-lookup"><span data-stu-id="1f58f-120">Expiration time.</span></span> <span data-ttu-id="1f58f-121">(Token werden nach 30 Minuten ablaufen, es sei denn, angeheftet (siehe die folgenden Beschreibungen in dieser Spalte).</span><span class="sxs-lookup"><span data-stu-id="1f58f-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f58f-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="1f58f-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="1f58f-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f58f-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1f58f-124">Die URL der übertragenen Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="1f58f-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f58f-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="1f58f-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="1f58f-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f58f-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1f58f-127">Die URL der Miniaturansicht für die übertragene Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="1f58f-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f58f-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="1f58f-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="1f58f-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="1f58f-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="1f58f-130">Timestamp für den eigentlichen Dateiübertragungsvorgang (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="1f58f-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f58f-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="1f58f-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="1f58f-132">bit</span><span class="sxs-lookup"><span data-stu-id="1f58f-132">bit</span></span></p></td>
<td><p><span data-ttu-id="1f58f-133">True, wenn Upload; False, wenn Download (für Compliance-Dienstnutzung).</span><span class="sxs-lookup"><span data-stu-id="1f58f-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f58f-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="1f58f-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="1f58f-135">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1f58f-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1f58f-136">True, wenn Token angeheftet ist.</span><span class="sxs-lookup"><span data-stu-id="1f58f-136">True if token is pinned.</span></span> <span data-ttu-id="1f58f-137">Sie wird verwendet, um das Token in der Tabelle beizubehalten, bis der Kompatibilitätsdienst die entsprechenden Felder aus ihm abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="1f58f-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1f58f-138">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1f58f-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f58f-139">Spalte</span><span class="sxs-lookup"><span data-stu-id="1f58f-139">Column</span></span></th>
<th><span data-ttu-id="1f58f-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f58f-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f58f-141">FileToken</span><span class="sxs-lookup"><span data-stu-id="1f58f-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="1f58f-142">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="1f58f-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f58f-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1f58f-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="1f58f-144">Fremdschlüssel mit Lookup in der tblNode. nodeGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1f58f-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

