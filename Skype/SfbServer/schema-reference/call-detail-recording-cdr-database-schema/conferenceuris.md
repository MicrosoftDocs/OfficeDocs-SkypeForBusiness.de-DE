---
title: ConferenceUris-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Die ConfereneUris-Tabelle ist eine Tabelle, die speichert eine Liste der verschiedenen Konferenz-URIs, die in der Datenbank aufgezeichnet konferenzsitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Konferenz-URI.
ms.openlocfilehash: 70cb3ccecf1c63dd128cbffd6ac205e77c771835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901066"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fd74f-104">ConferenceUris-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd74f-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fd74f-105">Die ConfereneUris-Tabelle ist eine Tabelle, die speichert eine Liste der verschiedenen Konferenz-URIs, die in der Datenbank aufgezeichnet konferenzsitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="fd74f-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="fd74f-106">Jeder Datensatz in der Tabelle steht für eine Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="fd74f-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="fd74f-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="fd74f-107">**Column**</span></span>|<span data-ttu-id="fd74f-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="fd74f-108">**Data Type**</span></span>|<span data-ttu-id="fd74f-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="fd74f-109">**Key/Index**</span></span>|<span data-ttu-id="fd74f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="fd74f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd74f-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="fd74f-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="fd74f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fd74f-112">datetime</span></span>  <br/> |<span data-ttu-id="fd74f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fd74f-113">Primary</span></span>  <br/> |<span data-ttu-id="fd74f-114">Zeitstempel; zu internen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="fd74f-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="fd74f-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="fd74f-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="fd74f-116">int</span><span class="sxs-lookup"><span data-stu-id="fd74f-116">int</span></span>  <br/> |<span data-ttu-id="fd74f-117">Primary</span><span class="sxs-lookup"><span data-stu-id="fd74f-117">Primary</span></span>  <br/> |<span data-ttu-id="fd74f-118">Eindeutige Zahl, die diesen Konferenz-URI identifiziert.</span><span class="sxs-lookup"><span data-stu-id="fd74f-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="fd74f-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="fd74f-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="fd74f-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fd74f-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="fd74f-121">Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="fd74f-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="fd74f-122">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="fd74f-122">**Checksum**</span></span> <br/> |<span data-ttu-id="fd74f-123">int</span><span class="sxs-lookup"><span data-stu-id="fd74f-123">int</span></span>  <br/> ||<span data-ttu-id="fd74f-124">Prüfsumme der ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="fd74f-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="fd74f-125">Verwendet zum erhöht die Geschwindigkeit der Datenbank suchen.</span><span class="sxs-lookup"><span data-stu-id="fd74f-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="fd74f-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="fd74f-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="fd74f-127">int</span><span class="sxs-lookup"><span data-stu-id="fd74f-127">int</span></span>  <br/> |<span data-ttu-id="fd74f-128">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="fd74f-128">Foreign</span></span>  <br/> |<span data-ttu-id="fd74f-129">URI-Typ, wie etwa Conf:chat für Instant Messaging-Konferenz oder Conf:audio-video für Audio-Video-Konferenz.</span><span class="sxs-lookup"><span data-stu-id="fd74f-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="fd74f-130">Finden Sie weitere Informationen die [UriTypes-Tabelle](uritypes.md) -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fd74f-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

