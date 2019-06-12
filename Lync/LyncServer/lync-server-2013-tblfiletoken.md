---
title: 'Lync Server 2013: tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="fb324-102">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb324-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb324-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fb324-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fb324-104">tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.</span><span class="sxs-lookup"><span data-stu-id="fb324-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="fb324-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="fb324-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb324-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="fb324-106">Column</span></span></th>
<th><span data-ttu-id="fb324-107">Typ</span><span class="sxs-lookup"><span data-stu-id="fb324-107">Type</span></span></th>
<th><span data-ttu-id="fb324-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb324-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb324-109">FileToken</span><span class="sxs-lookup"><span data-stu-id="fb324-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="fb324-110">nvarchar (50); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fb324-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="fb324-111">Eindeutiges Token (eine GUID).</span><span class="sxs-lookup"><span data-stu-id="fb324-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb324-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="fb324-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="fb324-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fb324-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fb324-114">Die ID des Prinzipals, der die Datei übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="fb324-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb324-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="fb324-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="fb324-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fb324-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="fb324-117">GUID des Chatroom-Knotens.</span><span class="sxs-lookup"><span data-stu-id="fb324-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb324-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="fb324-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="fb324-119">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fb324-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fb324-120">Ablaufzeit.</span><span class="sxs-lookup"><span data-stu-id="fb324-120">Expiration time.</span></span> <span data-ttu-id="fb324-121">(Token werden nach 30 Minuten ablaufen, es sei denn, angeheftet (siehe die folgenden Beschreibungen in dieser Spalte).</span><span class="sxs-lookup"><span data-stu-id="fb324-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb324-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="fb324-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="fb324-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fb324-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb324-124">Die URL der übertragenen Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="fb324-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb324-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="fb324-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="fb324-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fb324-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb324-127">Die URL der Miniaturansicht für die übertragene Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="fb324-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb324-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="fb324-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="fb324-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="fb324-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="fb324-130">Timestamp für den eigentlichen Dateiübertragungsvorgang (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="fb324-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb324-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="fb324-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="fb324-132">bit</span><span class="sxs-lookup"><span data-stu-id="fb324-132">bit</span></span></p></td>
<td><p><span data-ttu-id="fb324-133">True, wenn Upload; False, wenn Download (für Compliance-Dienstnutzung).</span><span class="sxs-lookup"><span data-stu-id="fb324-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb324-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="fb324-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="fb324-135">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fb324-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fb324-136">True, wenn Token angeheftet ist.</span><span class="sxs-lookup"><span data-stu-id="fb324-136">True if token is pinned.</span></span> <span data-ttu-id="fb324-137">Sie wird verwendet, um das Token in der Tabelle beizubehalten, bis der Kompatibilitätsdienst die entsprechenden Felder aus ihm abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="fb324-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="fb324-138">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="fb324-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb324-139">Spalte</span><span class="sxs-lookup"><span data-stu-id="fb324-139">Column</span></span></th>
<th><span data-ttu-id="fb324-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb324-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb324-141">FileToken</span><span class="sxs-lookup"><span data-stu-id="fb324-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="fb324-142">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="fb324-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb324-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="fb324-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="fb324-144">Fremdschlüssel mit Lookup in der tblNode. nodeGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fb324-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

