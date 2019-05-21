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
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Die Konferenz Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295013"
---
# <a name="conference-table"></a><span data-ttu-id="69a5e-104">Conference-Tabelle</span><span class="sxs-lookup"><span data-stu-id="69a5e-104">Conference table</span></span>
 
<span data-ttu-id="69a5e-105">Die Konferenz Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="69a5e-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="69a5e-106">Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="69a5e-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="69a5e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="69a5e-107">**Column**</span></span>|<span data-ttu-id="69a5e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="69a5e-108">**Data Type**</span></span>|<span data-ttu-id="69a5e-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="69a5e-109">**Key/Index**</span></span>|<span data-ttu-id="69a5e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="69a5e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69a5e-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="69a5e-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="69a5e-112">int</span><span class="sxs-lookup"><span data-stu-id="69a5e-112">int</span></span>  <br/> |<span data-ttu-id="69a5e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="69a5e-113">Primary</span></span>  <br/> |<span data-ttu-id="69a5e-114">Eindeutige Nummer, die diesen Konferenz Eintrag kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="69a5e-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="69a5e-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="69a5e-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="69a5e-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="69a5e-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="69a5e-117">eindeutigen</span><span class="sxs-lookup"><span data-stu-id="69a5e-117">unique</span></span>  <br/> |<span data-ttu-id="69a5e-118">Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.</span><span class="sxs-lookup"><span data-stu-id="69a5e-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="69a5e-119">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="69a5e-119">**Checksum**</span></span> <br/> |<span data-ttu-id="69a5e-120">int</span><span class="sxs-lookup"><span data-stu-id="69a5e-120">int</span></span>  <br/> |<span data-ttu-id="69a5e-121">Index</span><span class="sxs-lookup"><span data-stu-id="69a5e-121">index</span></span>  <br/> |<span data-ttu-id="69a5e-122">Die Prüfsumme des Konferenz-URIs.</span><span class="sxs-lookup"><span data-stu-id="69a5e-122">Checksum of the conference URI.</span></span> <span data-ttu-id="69a5e-123">Diese wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="69a5e-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="69a5e-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="69a5e-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="69a5e-125">datetime</span><span class="sxs-lookup"><span data-stu-id="69a5e-125">datetime</span></span>  <br/> ||<span data-ttu-id="69a5e-126">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="69a5e-126">For internal use only.</span></span>  <br/> |
   

