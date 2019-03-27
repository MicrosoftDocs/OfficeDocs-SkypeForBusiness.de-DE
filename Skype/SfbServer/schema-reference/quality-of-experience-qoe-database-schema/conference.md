---
title: Conference-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Die Konferenz-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874039"
---
# <a name="conference-table"></a><span data-ttu-id="7523c-104">Conference-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7523c-104">Conference table</span></span>
 
<span data-ttu-id="7523c-105">Die Konferenz-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7523c-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="7523c-106">Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7523c-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="7523c-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7523c-107">**Column**</span></span>|<span data-ttu-id="7523c-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7523c-108">**Data Type**</span></span>|<span data-ttu-id="7523c-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7523c-109">**Key/Index**</span></span>|<span data-ttu-id="7523c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7523c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7523c-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="7523c-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="7523c-112">int</span><span class="sxs-lookup"><span data-stu-id="7523c-112">int</span></span>  <br/> |<span data-ttu-id="7523c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7523c-113">Primary</span></span>  <br/> |<span data-ttu-id="7523c-114">Eindeutige Zahl, die diesen konferenzdatensatz identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7523c-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="7523c-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="7523c-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="7523c-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="7523c-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="7523c-117">eindeutige</span><span class="sxs-lookup"><span data-stu-id="7523c-117">unique</span></span>  <br/> |<span data-ttu-id="7523c-118">Konferenz-URI ist dies eine Konferenz ist, oder Dialogkennung, wenn dieser ist eine Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7523c-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="7523c-119">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="7523c-119">**Checksum**</span></span> <br/> |<span data-ttu-id="7523c-120">int</span><span class="sxs-lookup"><span data-stu-id="7523c-120">int</span></span>  <br/> |<span data-ttu-id="7523c-121">Index</span><span class="sxs-lookup"><span data-stu-id="7523c-121">index</span></span>  <br/> |<span data-ttu-id="7523c-122">Prüfsumme der Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="7523c-122">Checksum of the conference URI.</span></span> <span data-ttu-id="7523c-123">Intern wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="7523c-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="7523c-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7523c-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7523c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="7523c-125">datetime</span></span>  <br/> ||<span data-ttu-id="7523c-126">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="7523c-126">For internal use only.</span></span>  <br/> |
   

