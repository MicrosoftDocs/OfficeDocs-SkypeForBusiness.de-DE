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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814593"
---
# <a name="tblfiletoken"></a><span data-ttu-id="630ac-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="630ac-103">tblFileToken</span></span>
 
<span data-ttu-id="630ac-104">tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.</span><span class="sxs-lookup"><span data-stu-id="630ac-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="630ac-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="630ac-105">**Columns**</span></span>

|<span data-ttu-id="630ac-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="630ac-106">**Column**</span></span>|<span data-ttu-id="630ac-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="630ac-107">**Type**</span></span>|<span data-ttu-id="630ac-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="630ac-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="630ac-109">FileToken</span><span class="sxs-lookup"><span data-stu-id="630ac-109">fileToken</span></span>  <br/> |<span data-ttu-id="630ac-110">nvarchar (50); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="630ac-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="630ac-111">Eindeutiges Token (eine GUID).</span><span class="sxs-lookup"><span data-stu-id="630ac-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="630ac-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="630ac-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="630ac-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="630ac-113">int, not null</span></span>  <br/> |<span data-ttu-id="630ac-114">Die ID des Prinzipals, der die Datei übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="630ac-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="630ac-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="630ac-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="630ac-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="630ac-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="630ac-117">GUID des Chatroom-Knotens.</span><span class="sxs-lookup"><span data-stu-id="630ac-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="630ac-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="630ac-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="630ac-119">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="630ac-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="630ac-120">Ablaufzeit.</span><span class="sxs-lookup"><span data-stu-id="630ac-120">Expiration time.</span></span> <span data-ttu-id="630ac-121">(Token werden nach 30 Minuten ablaufen, es sei denn, angeheftet (siehe die folgenden Beschreibungen in dieser Spalte).</span><span class="sxs-lookup"><span data-stu-id="630ac-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="630ac-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="630ac-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="630ac-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="630ac-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="630ac-124">Die URL der übertragenen Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="630ac-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="630ac-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="630ac-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="630ac-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="630ac-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="630ac-127">Die URL der Miniaturansicht für die übertragene Datei (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="630ac-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="630ac-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="630ac-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="630ac-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="630ac-129">datetime2</span></span>  <br/> |<span data-ttu-id="630ac-130">Timestamp für den eigentlichen Dateiübertragungsvorgang (für die Verwendung des Kompatibilitätsdiensts).</span><span class="sxs-lookup"><span data-stu-id="630ac-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="630ac-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="630ac-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="630ac-132">bit</span><span class="sxs-lookup"><span data-stu-id="630ac-132">bit</span></span>  <br/> |<span data-ttu-id="630ac-133">True, wenn Upload; False, wenn Download (für Compliance-Dienstnutzung).</span><span class="sxs-lookup"><span data-stu-id="630ac-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="630ac-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="630ac-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="630ac-135">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="630ac-135">bit, not null</span></span>  <br/> |<span data-ttu-id="630ac-136">True, wenn Token angeheftet ist.</span><span class="sxs-lookup"><span data-stu-id="630ac-136">True if token is pinned.</span></span> <span data-ttu-id="630ac-137">Sie wird verwendet, um das Token in der Tabelle beizubehalten, bis der Kompatibilitätsdienst die entsprechenden Felder aus ihm abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="630ac-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="630ac-138">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="630ac-138">**Keys**</span></span>

|<span data-ttu-id="630ac-139">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="630ac-139">**Column**</span></span>|<span data-ttu-id="630ac-140">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="630ac-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="630ac-141">FileToken</span><span class="sxs-lookup"><span data-stu-id="630ac-141">fileToken</span></span>  <br/> |<span data-ttu-id="630ac-142">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="630ac-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="630ac-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="630ac-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="630ac-144">Fremdschlüssel mit Lookup in der tblNode. nodeGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="630ac-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

