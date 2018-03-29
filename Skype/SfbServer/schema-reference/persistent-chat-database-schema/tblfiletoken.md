---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: TblFileToken enthält temporäre Token für die Dateiübertragung.
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a><span data-ttu-id="eae6b-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="eae6b-103">tblFileToken</span></span>
 
<span data-ttu-id="eae6b-104">TblFileToken enthält temporäre Token für die Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="eae6b-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="eae6b-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="eae6b-105">**Columns**</span></span>

|<span data-ttu-id="eae6b-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="eae6b-106">**Column**</span></span>|<span data-ttu-id="eae6b-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="eae6b-107">**Type**</span></span>|<span data-ttu-id="eae6b-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="eae6b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eae6b-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="eae6b-109">fileToken</span></span>  <br/> |<span data-ttu-id="eae6b-110">Nvarchar (50), nicht null</span><span class="sxs-lookup"><span data-stu-id="eae6b-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="eae6b-111">Eindeutiges Token (eine GUID).</span><span class="sxs-lookup"><span data-stu-id="eae6b-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="eae6b-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="eae6b-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="eae6b-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="eae6b-113">int, not null</span></span>  <br/> |<span data-ttu-id="eae6b-114">ID des Prinzipals, der die Datei überträgt.</span><span class="sxs-lookup"><span data-stu-id="eae6b-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="eae6b-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="eae6b-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="eae6b-116">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="eae6b-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="eae6b-117">GUID des chatroomknotens.</span><span class="sxs-lookup"><span data-stu-id="eae6b-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="eae6b-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="eae6b-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="eae6b-119">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="eae6b-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="eae6b-120">Ablaufzeit.</span><span class="sxs-lookup"><span data-stu-id="eae6b-120">Expiration time.</span></span> <span data-ttu-id="eae6b-121">(Token laufen ab nach 30 Minuten, es sei denn, fixiert (siehe die folgenden Beschreibungen in dieser Spalte).</span><span class="sxs-lookup"><span data-stu-id="eae6b-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="eae6b-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="eae6b-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="eae6b-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eae6b-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eae6b-124">URL der übertragenen Datei (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="eae6b-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="eae6b-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="eae6b-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="eae6b-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eae6b-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eae6b-127">URL des Miniaturbilds der übertragenen Datei (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="eae6b-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="eae6b-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="eae6b-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="eae6b-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="eae6b-129">datetime2</span></span>  <br/> |<span data-ttu-id="eae6b-130">Zeitstempel für die tatsächliche Dateiübertragung (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="eae6b-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="eae6b-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="eae6b-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="eae6b-132">bit</span><span class="sxs-lookup"><span data-stu-id="eae6b-132">bit</span></span>  <br/> |<span data-ttu-id="eae6b-133">True, wenn hochzuladen. False, wenn herunterladen (für den Kompatibilitätsdienst).</span><span class="sxs-lookup"><span data-stu-id="eae6b-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="eae6b-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="eae6b-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="eae6b-135">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="eae6b-135">bit, not null</span></span>  <br/> |<span data-ttu-id="eae6b-136">True, wenn Token fixiert ist.</span><span class="sxs-lookup"><span data-stu-id="eae6b-136">True if token is pinned.</span></span> <span data-ttu-id="eae6b-137">Es wird verwendet, um das Token in der Tabelle beibehalten, bis kompatibilitätsdienst Möglichkeit, die entsprechenden Felder daraus abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="eae6b-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="eae6b-138">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="eae6b-138">**Keys**</span></span>

|<span data-ttu-id="eae6b-139">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="eae6b-139">**Column**</span></span>|<span data-ttu-id="eae6b-140">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="eae6b-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eae6b-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="eae6b-141">fileToken</span></span>  <br/> |<span data-ttu-id="eae6b-142">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="eae6b-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="eae6b-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="eae6b-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="eae6b-144">Fremdschlüssel mit Abfrage der tblNode.nodeGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="eae6b-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

