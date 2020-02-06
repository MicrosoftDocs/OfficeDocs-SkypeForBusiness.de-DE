---
title: Conference-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Die Konferenz Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810303"
---
# <a name="conference-table"></a><span data-ttu-id="34607-104">Conference-Tabelle</span><span class="sxs-lookup"><span data-stu-id="34607-104">Conference table</span></span>
 
<span data-ttu-id="34607-105">Die Konferenz Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="34607-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="34607-106">Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="34607-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="34607-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="34607-107">**Column**</span></span>|<span data-ttu-id="34607-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="34607-108">**Data Type**</span></span>|<span data-ttu-id="34607-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="34607-109">**Key/Index**</span></span>|<span data-ttu-id="34607-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="34607-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34607-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="34607-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="34607-112">int</span><span class="sxs-lookup"><span data-stu-id="34607-112">int</span></span>  <br/> |<span data-ttu-id="34607-113">Primary</span><span class="sxs-lookup"><span data-stu-id="34607-113">Primary</span></span>  <br/> |<span data-ttu-id="34607-114">Eindeutige Nummer, die diesen Konferenz Eintrag kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="34607-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="34607-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="34607-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="34607-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34607-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="34607-117">eindeutigen</span><span class="sxs-lookup"><span data-stu-id="34607-117">unique</span></span>  <br/> |<span data-ttu-id="34607-118">Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.</span><span class="sxs-lookup"><span data-stu-id="34607-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="34607-119">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="34607-119">**Checksum**</span></span> <br/> |<span data-ttu-id="34607-120">int</span><span class="sxs-lookup"><span data-stu-id="34607-120">int</span></span>  <br/> |<span data-ttu-id="34607-121">Index</span><span class="sxs-lookup"><span data-stu-id="34607-121">index</span></span>  <br/> |<span data-ttu-id="34607-122">Die Prüfsumme des Konferenz-URIs.</span><span class="sxs-lookup"><span data-stu-id="34607-122">Checksum of the conference URI.</span></span> <span data-ttu-id="34607-123">Diese wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="34607-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="34607-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="34607-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="34607-125">datetime</span><span class="sxs-lookup"><span data-stu-id="34607-125">datetime</span></span>  <br/> ||<span data-ttu-id="34607-126">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="34607-126">For internal use only.</span></span>  <br/> |
   

