---
title: Conference-Tabelle
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
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a><span data-ttu-id="50448-104">Conference-Tabelle</span><span class="sxs-lookup"><span data-stu-id="50448-104">Conference table</span></span>
 
<span data-ttu-id="50448-105">Die Konferenz-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="50448-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="50448-106">Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="50448-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="50448-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="50448-107">**Column**</span></span>|<span data-ttu-id="50448-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="50448-108">**Data Type**</span></span>|<span data-ttu-id="50448-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="50448-109">**Key/Index**</span></span>|<span data-ttu-id="50448-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="50448-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50448-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="50448-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="50448-112">int</span><span class="sxs-lookup"><span data-stu-id="50448-112">int</span></span>  <br/> |<span data-ttu-id="50448-113">Primary</span><span class="sxs-lookup"><span data-stu-id="50448-113">Primary</span></span>  <br/> |<span data-ttu-id="50448-114">Eindeutige Zahl, die diesen konferenzdatensatz identifiziert.</span><span class="sxs-lookup"><span data-stu-id="50448-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="50448-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="50448-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="50448-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="50448-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="50448-117">eindeutige</span><span class="sxs-lookup"><span data-stu-id="50448-117">unique</span></span>  <br/> |<span data-ttu-id="50448-118">Konferenz-URI ist dies eine Konferenz ist, oder Dialogkennung, wenn dieser ist eine Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="50448-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="50448-119">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="50448-119">**Checksum**</span></span> <br/> |<span data-ttu-id="50448-120">int</span><span class="sxs-lookup"><span data-stu-id="50448-120">int</span></span>  <br/> |<span data-ttu-id="50448-121">Index</span><span class="sxs-lookup"><span data-stu-id="50448-121">index</span></span>  <br/> |<span data-ttu-id="50448-122">Prüfsumme der Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="50448-122">Checksum of the conference URI.</span></span> <span data-ttu-id="50448-123">Intern wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="50448-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="50448-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="50448-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="50448-125">datetime</span><span class="sxs-lookup"><span data-stu-id="50448-125">datetime</span></span>  <br/> ||<span data-ttu-id="50448-126">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="50448-126">For internal use only.</span></span>  <br/> |
   

