---
title: ConferenceUris-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Die ConfereneUris-Tabelle ist eine Tabelle, die speichert eine Liste der verschiedenen Konferenz-URIs, die in der Datenbank aufgezeichnet konferenzsitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Konferenz-URI.
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213214"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="44bdf-104">ConferenceUris-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="44bdf-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="44bdf-105">Die ConfereneUris-Tabelle ist eine Tabelle, die speichert eine Liste der verschiedenen Konferenz-URIs, die in der Datenbank aufgezeichnet konferenzsitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="44bdf-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="44bdf-106">Jeder Datensatz in der Tabelle steht für eine Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="44bdf-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="44bdf-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="44bdf-107">**Column**</span></span>|<span data-ttu-id="44bdf-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="44bdf-108">**Data Type**</span></span>|<span data-ttu-id="44bdf-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="44bdf-109">**Key/Index**</span></span>|<span data-ttu-id="44bdf-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="44bdf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44bdf-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="44bdf-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="44bdf-112">datetime</span><span class="sxs-lookup"><span data-stu-id="44bdf-112">datetime</span></span>  <br/> |<span data-ttu-id="44bdf-113">Primary</span><span class="sxs-lookup"><span data-stu-id="44bdf-113">Primary</span></span>  <br/> |<span data-ttu-id="44bdf-114">Zeitstempel; zu internen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="44bdf-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="44bdf-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="44bdf-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="44bdf-116">int</span><span class="sxs-lookup"><span data-stu-id="44bdf-116">int</span></span>  <br/> |<span data-ttu-id="44bdf-117">Primary</span><span class="sxs-lookup"><span data-stu-id="44bdf-117">Primary</span></span>  <br/> |<span data-ttu-id="44bdf-118">Eindeutige Zahl, die diesen Konferenz-URI identifiziert.</span><span class="sxs-lookup"><span data-stu-id="44bdf-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="44bdf-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="44bdf-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="44bdf-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="44bdf-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="44bdf-121">Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="44bdf-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="44bdf-122">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="44bdf-122">**Checksum**</span></span> <br/> |<span data-ttu-id="44bdf-123">int</span><span class="sxs-lookup"><span data-stu-id="44bdf-123">int</span></span>  <br/> ||<span data-ttu-id="44bdf-124">Prüfsumme der ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="44bdf-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="44bdf-125">Verwendet zum erhöht die Geschwindigkeit der Datenbank suchen.</span><span class="sxs-lookup"><span data-stu-id="44bdf-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="44bdf-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="44bdf-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="44bdf-127">int</span><span class="sxs-lookup"><span data-stu-id="44bdf-127">int</span></span>  <br/> |<span data-ttu-id="44bdf-128">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="44bdf-128">Foreign</span></span>  <br/> |<span data-ttu-id="44bdf-129">URI-Typ, wie etwa Conf:chat für Instant Messaging-Konferenz oder Conf:audio-video für Audio-Video-Konferenz.</span><span class="sxs-lookup"><span data-stu-id="44bdf-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="44bdf-130">Finden Sie weitere Informationen die [UriTypes-Tabelle](uritypes.md) -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="44bdf-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

