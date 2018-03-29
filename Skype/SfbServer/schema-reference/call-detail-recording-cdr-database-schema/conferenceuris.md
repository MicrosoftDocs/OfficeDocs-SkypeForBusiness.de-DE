---
title: ConferenceUris-Tabelle in Skype für Business Server 2015
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
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1106e-104">ConferenceUris-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1106e-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1106e-105">Die ConfereneUris-Tabelle ist eine Tabelle, die speichert eine Liste der verschiedenen Konferenz-URIs, die in der Datenbank aufgezeichnet konferenzsitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="1106e-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="1106e-106">Jeder Datensatz in der Tabelle steht für eine Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="1106e-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="1106e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1106e-107">**Column**</span></span>|<span data-ttu-id="1106e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="1106e-108">**Data Type**</span></span>|<span data-ttu-id="1106e-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="1106e-109">**Key/Index**</span></span>|<span data-ttu-id="1106e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="1106e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1106e-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1106e-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1106e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1106e-112">datetime</span></span>  <br/> |<span data-ttu-id="1106e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1106e-113">Primary</span></span>  <br/> |<span data-ttu-id="1106e-114">Zeitstempel; zu internen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="1106e-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="1106e-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="1106e-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="1106e-116">int</span><span class="sxs-lookup"><span data-stu-id="1106e-116">int</span></span>  <br/> |<span data-ttu-id="1106e-117">Primary</span><span class="sxs-lookup"><span data-stu-id="1106e-117">Primary</span></span>  <br/> |<span data-ttu-id="1106e-118">Eindeutige Zahl, die diesen Konferenz-URI identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1106e-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="1106e-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="1106e-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="1106e-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="1106e-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="1106e-121">Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="1106e-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="1106e-122">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="1106e-122">**Checksum**</span></span> <br/> |<span data-ttu-id="1106e-123">int</span><span class="sxs-lookup"><span data-stu-id="1106e-123">int</span></span>  <br/> ||<span data-ttu-id="1106e-124">Prüfsumme der ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="1106e-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="1106e-125">Verwendet zum erhöht die Geschwindigkeit der Datenbank suchen.</span><span class="sxs-lookup"><span data-stu-id="1106e-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="1106e-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="1106e-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="1106e-127">int</span><span class="sxs-lookup"><span data-stu-id="1106e-127">int</span></span>  <br/> |<span data-ttu-id="1106e-128">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="1106e-128">Foreign</span></span>  <br/> |<span data-ttu-id="1106e-129">URI-Typ, wie etwa Conf:chat für Instant Messaging-Konferenz oder Conf:audio-video für Audio-Video-Konferenz.</span><span class="sxs-lookup"><span data-stu-id="1106e-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="1106e-130">Finden Sie weitere Informationen die [UriTypes-Tabelle](uritypes.md) -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1106e-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

