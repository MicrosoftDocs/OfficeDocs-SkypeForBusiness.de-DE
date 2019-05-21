---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295405"
---
# <a name="tblfiletoken"></a><span data-ttu-id="c7575-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="c7575-103">tblFileToken</span></span>
 
<span data-ttu-id="c7575-104">tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.</span><span class="sxs-lookup"><span data-stu-id="c7575-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="c7575-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c7575-105">**Columns**</span></span>

|<span data-ttu-id="c7575-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c7575-106">**Column**</span></span>|<span data-ttu-id="c7575-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c7575-107">**Type**</span></span>|<span data-ttu-id="c7575-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c7575-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7575-109">FileToken</span><span class="sxs-lookup"><span data-stu-id="c7575-109">fileToken</span></span>  <br/> |<span data-ttu-id="c7575-110">nvarchar (50); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c7575-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="c7575-111">Eindeutiges Token (eine GUID).</span><span class="sxs-lookup"><span data-stu-id="c7575-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="c7575-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="c7575-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="c7575-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c7575-113">int, not null</span></span>  <br/> |<span data-ttu-id="c7575-114">Die ID des Prinzipals, der die Datei übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="c7575-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="c7575-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="c7575-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="c7575-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c7575-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="c7575-117">GUID des Chatroom-Knotens.</span><span class="sxs-lookup"><span data-stu-id="c7575-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="c7575-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="c7575-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="c7575-119">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c7575-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="c7575-120">Ablaufzeit.</span><span class="sxs-lookup"><span data-stu-id="c7575-120">Expiration time.</span></span> <span data-ttu-id="c7575-121">(Token werden nach 30 Minuten ablaufen, es sei denn, angeheftet (siehe die folgenden Beschreibungen in dieser Spalte).</span><span class="sxs-lookup"><span data-stu-id="c7575-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="c7575-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="c7575-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="c7575-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c7575-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c7575-124">Die URL der übertragenen Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="c7575-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c7575-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="c7575-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="c7575-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c7575-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c7575-127">Die URL der Miniaturansicht für die übertragene Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="c7575-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c7575-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="c7575-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="c7575-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="c7575-129">datetime2</span></span>  <br/> |<span data-ttu-id="c7575-130">Timestamp für den eigentlichen Dateiübertragungsvorgang (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="c7575-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c7575-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="c7575-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="c7575-132">bit</span><span class="sxs-lookup"><span data-stu-id="c7575-132">bit</span></span>  <br/> |<span data-ttu-id="c7575-133">True, wenn Upload; False, wenn Download (für Compliance-Dienstnutzung).</span><span class="sxs-lookup"><span data-stu-id="c7575-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c7575-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="c7575-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="c7575-135">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c7575-135">bit, not null</span></span>  <br/> |<span data-ttu-id="c7575-136">True, wenn Token angeheftet ist.</span><span class="sxs-lookup"><span data-stu-id="c7575-136">True if token is pinned.</span></span> <span data-ttu-id="c7575-137">Sie wird verwendet, um das Token in der Tabelle beizubehalten, bis der Kompatibilitätsdienst die entsprechenden Felder aus ihm abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="c7575-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="c7575-138">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="c7575-138">**Keys**</span></span>

|<span data-ttu-id="c7575-139">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c7575-139">**Column**</span></span>|<span data-ttu-id="c7575-140">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c7575-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7575-141">FileToken</span><span class="sxs-lookup"><span data-stu-id="c7575-141">fileToken</span></span>  <br/> |<span data-ttu-id="c7575-142">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="c7575-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c7575-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="c7575-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="c7575-144">Fremdschlüssel mit Lookup in der tblNode. nodeGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c7575-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

