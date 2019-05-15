---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: "\"tblcompliancedata\" enthält die genehmigungsereignisse, die nicht vom kompatibilitätsadapter noch verarbeitet wurden."
ms.openlocfilehash: 88319da90c1f3e03b6ca3e441259972f51d0bcf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929931"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="87e49-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="87e49-103">tblComplianceData</span></span>
 
<span data-ttu-id="87e49-104">"tblcompliancedata" enthält die genehmigungsereignisse, die nicht vom kompatibilitätsadapter noch verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="87e49-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="87e49-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="87e49-105">**Columns**</span></span>

|<span data-ttu-id="87e49-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="87e49-106">**Column**</span></span>|<span data-ttu-id="87e49-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="87e49-107">**Type**</span></span>|<span data-ttu-id="87e49-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="87e49-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="87e49-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="87e49-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="87e49-110">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="87e49-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="87e49-111">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="87e49-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="87e49-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="87e49-112">entryDate</span></span>  <br/> |<span data-ttu-id="87e49-113">Smalldatetime, nicht null</span><span class="sxs-lookup"><span data-stu-id="87e49-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="87e49-114">Zeitpunkt des Einfügevorgangs (möglicherweise weit in der Zukunft für CmplType = 9, da der Eintrag in diesem Fall nur ein Platzhalter ist).</span><span class="sxs-lookup"><span data-stu-id="87e49-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="87e49-115">"cmpltype"</span><span class="sxs-lookup"><span data-stu-id="87e49-115">cmplType</span></span>  <br/> |<span data-ttu-id="87e49-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="87e49-116">int, not null</span></span>  <br/> | <span data-ttu-id="87e49-117">Der Typ des kompatibilitätsereignisses:</span><span class="sxs-lookup"><span data-stu-id="87e49-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="87e49-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="87e49-118">1: Chat</span></span> <br/>  <span data-ttu-id="87e49-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="87e49-119">2: Backchat</span></span> <br/>  <span data-ttu-id="87e49-120">3: Dateidownload</span><span class="sxs-lookup"><span data-stu-id="87e49-120">3: File download</span></span> <br/>  <span data-ttu-id="87e49-121">4: Dateiupload</span><span class="sxs-lookup"><span data-stu-id="87e49-121">4: File upload</span></span> <br/>  <span data-ttu-id="87e49-122">9: vorläufige Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="87e49-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="87e49-123">10: chatlöschung (mit Ersatz)</span><span class="sxs-lookup"><span data-stu-id="87e49-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="87e49-124">11: chatbereinigung</span><span class="sxs-lookup"><span data-stu-id="87e49-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="87e49-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="87e49-125">cmplTime</span></span>  <br/> |<span data-ttu-id="87e49-126">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="87e49-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="87e49-127">Zeitstempel für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="87e49-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="87e49-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="87e49-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="87e49-129">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="87e49-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="87e49-130">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="87e49-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="87e49-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="87e49-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="87e49-132">bigint</span><span class="sxs-lookup"><span data-stu-id="87e49-132">bigint</span></span>  <br/> |<span data-ttu-id="87e49-133">Chat-ID (entsprechend der Tabelle "tblchat.chatid").</span><span class="sxs-lookup"><span data-stu-id="87e49-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="87e49-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="87e49-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="87e49-135">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="87e49-135">int, not null</span></span>  <br/> |<span data-ttu-id="87e49-136">Prinzipal-ID des bereitstellers (entsprechend der tblPrincipal.prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="87e49-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="87e49-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="87e49-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="87e49-138">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="87e49-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="87e49-139">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="87e49-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="87e49-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="87e49-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="87e49-141">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="87e49-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="87e49-142">Nachricht (Codierung abhängig "cmpltype").</span><span class="sxs-lookup"><span data-stu-id="87e49-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="87e49-143">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="87e49-143">**Key**</span></span>

|<span data-ttu-id="87e49-144">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="87e49-144">**Column**</span></span>|<span data-ttu-id="87e49-145">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="87e49-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="87e49-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="87e49-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="87e49-147">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="87e49-147">Primary key.</span></span>  <br/> |
   

