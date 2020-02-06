---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData enthält die Konformitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814663"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="4df41-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="4df41-103">tblComplianceData</span></span>
 
<span data-ttu-id="4df41-104">tblComplianceData enthält die Konformitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="4df41-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="4df41-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="4df41-105">**Columns**</span></span>

|<span data-ttu-id="4df41-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4df41-106">**Column**</span></span>|<span data-ttu-id="4df41-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4df41-107">**Type**</span></span>|<span data-ttu-id="4df41-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4df41-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4df41-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="4df41-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="4df41-110">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4df41-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="4df41-111">Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="4df41-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="4df41-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="4df41-112">entryDate</span></span>  <br/> |<span data-ttu-id="4df41-113">smalldatetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4df41-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="4df41-114">Zeitpunkt der Einfügung (kann für cmplType = 9 weit in der Zukunft liegen, da der Eintrag nur ein Platzhalter in diesem Fall ist).</span><span class="sxs-lookup"><span data-stu-id="4df41-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="4df41-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="4df41-115">cmplType</span></span>  <br/> |<span data-ttu-id="4df41-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4df41-116">int, not null</span></span>  <br/> | <span data-ttu-id="4df41-117">Art des Konformitäts Ereignisses:</span><span class="sxs-lookup"><span data-stu-id="4df41-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="4df41-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="4df41-118">1: Chat</span></span> <br/>  <span data-ttu-id="4df41-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="4df41-119">2: Backchat</span></span> <br/>  <span data-ttu-id="4df41-120">3: Herunterladen von Dateien</span><span class="sxs-lookup"><span data-stu-id="4df41-120">3: File download</span></span> <br/>  <span data-ttu-id="4df41-121">4: Hochladen von Dateien</span><span class="sxs-lookup"><span data-stu-id="4df41-121">4: File upload</span></span> <br/>  <span data-ttu-id="4df41-122">9: provisorische Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="4df41-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="4df41-123">10: Löschen des Chats (mit Replace)</span><span class="sxs-lookup"><span data-stu-id="4df41-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="4df41-124">11: Chat-Bereinigung</span><span class="sxs-lookup"><span data-stu-id="4df41-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="4df41-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="4df41-125">cmplTime</span></span>  <br/> |<span data-ttu-id="4df41-126">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4df41-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="4df41-127">Zeitstempel für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4df41-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="4df41-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="4df41-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="4df41-129">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4df41-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="4df41-130">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="4df41-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="4df41-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="4df41-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="4df41-132">bigint</span><span class="sxs-lookup"><span data-stu-id="4df41-132">bigint</span></span>  <br/> |<span data-ttu-id="4df41-133">Chat-ID (entsprechend der tblChat. Chat-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="4df41-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="4df41-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="4df41-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="4df41-135">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4df41-135">int, not null</span></span>  <br/> |<span data-ttu-id="4df41-136">Prinzipal-ID des Plakats (entsprechend der tblPrincipal. prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="4df41-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="4df41-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="4df41-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="4df41-138">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4df41-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="4df41-139">Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="4df41-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="4df41-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="4df41-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="4df41-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="4df41-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="4df41-142">Nachricht (Codierung hängt von cmplType ab).</span><span class="sxs-lookup"><span data-stu-id="4df41-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="4df41-143">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="4df41-143">**Key**</span></span>

|<span data-ttu-id="4df41-144">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4df41-144">**Column**</span></span>|<span data-ttu-id="4df41-145">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4df41-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4df41-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="4df41-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="4df41-147">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="4df41-147">Primary key.</span></span>  <br/> |
   

