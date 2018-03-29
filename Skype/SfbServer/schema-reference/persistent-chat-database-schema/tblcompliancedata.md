---
title: "\"tblcompliancedata\""
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: "\"tblcompliancedata\" enthält die genehmigungsereignisse, die nicht vom kompatibilitätsadapter noch verarbeitet wurden."
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a><span data-ttu-id="46f3a-103">"tblcompliancedata"</span><span class="sxs-lookup"><span data-stu-id="46f3a-103">tblComplianceData</span></span>
 
<span data-ttu-id="46f3a-104">"tblcompliancedata" enthält die genehmigungsereignisse, die nicht vom kompatibilitätsadapter noch verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="46f3a-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="46f3a-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="46f3a-105">**Columns**</span></span>

|<span data-ttu-id="46f3a-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="46f3a-106">**Column**</span></span>|<span data-ttu-id="46f3a-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="46f3a-107">**Type**</span></span>|<span data-ttu-id="46f3a-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="46f3a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46f3a-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="46f3a-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="46f3a-110">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="46f3a-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="46f3a-111">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="46f3a-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="46f3a-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="46f3a-112">entryDate</span></span>  <br/> |<span data-ttu-id="46f3a-113">Smalldatetime, nicht null</span><span class="sxs-lookup"><span data-stu-id="46f3a-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="46f3a-114">Zeitpunkt des Einfügevorgangs (möglicherweise weit in der Zukunft für CmplType = 9, da der Eintrag in diesem Fall nur ein Platzhalter ist).</span><span class="sxs-lookup"><span data-stu-id="46f3a-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="46f3a-115">"cmpltype"</span><span class="sxs-lookup"><span data-stu-id="46f3a-115">cmplType</span></span>  <br/> |<span data-ttu-id="46f3a-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="46f3a-116">int, not null</span></span>  <br/> | <span data-ttu-id="46f3a-117">Der Typ des kompatibilitätsereignisses:</span><span class="sxs-lookup"><span data-stu-id="46f3a-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="46f3a-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="46f3a-118">1: Chat</span></span> <br/>  <span data-ttu-id="46f3a-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="46f3a-119">2: Backchat</span></span> <br/>  <span data-ttu-id="46f3a-120">3: Dateidownload</span><span class="sxs-lookup"><span data-stu-id="46f3a-120">3: File download</span></span> <br/>  <span data-ttu-id="46f3a-121">4: Dateiupload</span><span class="sxs-lookup"><span data-stu-id="46f3a-121">4: File upload</span></span> <br/>  <span data-ttu-id="46f3a-122">9: vorläufige Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="46f3a-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="46f3a-123">10: chatlöschung (mit Ersatz)</span><span class="sxs-lookup"><span data-stu-id="46f3a-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="46f3a-124">11: chatbereinigung</span><span class="sxs-lookup"><span data-stu-id="46f3a-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="46f3a-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="46f3a-125">cmplTime</span></span>  <br/> |<span data-ttu-id="46f3a-126">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="46f3a-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="46f3a-127">Zeitstempel für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="46f3a-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="46f3a-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="46f3a-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="46f3a-129">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="46f3a-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="46f3a-130">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="46f3a-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="46f3a-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="46f3a-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="46f3a-132">bigint</span><span class="sxs-lookup"><span data-stu-id="46f3a-132">bigint</span></span>  <br/> |<span data-ttu-id="46f3a-133">Chat-ID (entsprechend der Tabelle "tblchat.chatid").</span><span class="sxs-lookup"><span data-stu-id="46f3a-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="46f3a-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="46f3a-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="46f3a-135">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="46f3a-135">int, not null</span></span>  <br/> |<span data-ttu-id="46f3a-136">Prinzipal-ID des bereitstellers (entsprechend der tblPrincipal.prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="46f3a-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="46f3a-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="46f3a-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="46f3a-138">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="46f3a-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="46f3a-139">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="46f3a-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="46f3a-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="46f3a-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="46f3a-141">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="46f3a-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="46f3a-142">Nachricht (Codierung abhängig "cmpltype").</span><span class="sxs-lookup"><span data-stu-id="46f3a-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="46f3a-143">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="46f3a-143">**Key**</span></span>

|<span data-ttu-id="46f3a-144">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="46f3a-144">**Column**</span></span>|<span data-ttu-id="46f3a-145">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="46f3a-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46f3a-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="46f3a-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="46f3a-147">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="46f3a-147">Primary key.</span></span>  <br/> |
   

