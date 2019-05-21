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
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData enthält die Konformitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295510"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="ced08-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="ced08-103">tblComplianceData</span></span>
 
<span data-ttu-id="ced08-104">tblComplianceData enthält die Konformitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="ced08-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="ced08-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="ced08-105">**Columns**</span></span>

|<span data-ttu-id="ced08-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ced08-106">**Column**</span></span>|<span data-ttu-id="ced08-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ced08-107">**Type**</span></span>|<span data-ttu-id="ced08-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ced08-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ced08-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="ced08-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="ced08-110">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ced08-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="ced08-111">Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="ced08-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="ced08-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="ced08-112">entryDate</span></span>  <br/> |<span data-ttu-id="ced08-113">smalldatetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ced08-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="ced08-114">Zeitpunkt der Einfügung (kann für cmplType = 9 weit in der Zukunft liegen, da der Eintrag nur ein Platzhalter in diesem Fall ist).</span><span class="sxs-lookup"><span data-stu-id="ced08-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="ced08-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="ced08-115">cmplType</span></span>  <br/> |<span data-ttu-id="ced08-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ced08-116">int, not null</span></span>  <br/> | <span data-ttu-id="ced08-117">Art des Konformitäts Ereignisses:</span><span class="sxs-lookup"><span data-stu-id="ced08-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="ced08-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="ced08-118">1: Chat</span></span> <br/>  <span data-ttu-id="ced08-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="ced08-119">2: Backchat</span></span> <br/>  <span data-ttu-id="ced08-120">3: Herunterladen von Dateien</span><span class="sxs-lookup"><span data-stu-id="ced08-120">3: File download</span></span> <br/>  <span data-ttu-id="ced08-121">4: Hochladen von Dateien</span><span class="sxs-lookup"><span data-stu-id="ced08-121">4: File upload</span></span> <br/>  <span data-ttu-id="ced08-122">9: provisorische Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="ced08-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="ced08-123">10: Löschen des Chats (mit Replace)</span><span class="sxs-lookup"><span data-stu-id="ced08-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="ced08-124">11: Chat-Bereinigung</span><span class="sxs-lookup"><span data-stu-id="ced08-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="ced08-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="ced08-125">cmplTime</span></span>  <br/> |<span data-ttu-id="ced08-126">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ced08-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="ced08-127">Zeitstempel für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ced08-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="ced08-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="ced08-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="ced08-129">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ced08-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ced08-130">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="ced08-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="ced08-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="ced08-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="ced08-132">bigint</span><span class="sxs-lookup"><span data-stu-id="ced08-132">bigint</span></span>  <br/> |<span data-ttu-id="ced08-133">Chat-ID (entsprechend der tblChat. Chat-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="ced08-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="ced08-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="ced08-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="ced08-135">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ced08-135">int, not null</span></span>  <br/> |<span data-ttu-id="ced08-136">Prinzipal-ID des Plakats (entsprechend der tblPrincipal. prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="ced08-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="ced08-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="ced08-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="ced08-138">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ced08-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ced08-139">Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="ced08-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="ced08-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="ced08-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="ced08-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ced08-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="ced08-142">Nachricht (Codierung hängt von cmplType ab).</span><span class="sxs-lookup"><span data-stu-id="ced08-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="ced08-143">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="ced08-143">**Key**</span></span>

|<span data-ttu-id="ced08-144">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ced08-144">**Column**</span></span>|<span data-ttu-id="ced08-145">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ced08-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ced08-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="ced08-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="ced08-147">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="ced08-147">Primary key.</span></span>  <br/> |
   

