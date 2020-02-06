---
title: ConferenceUris-Tabelle in Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815313"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ff260-104">ConferenceUris-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ff260-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ff260-105">Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="ff260-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="ff260-106">Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="ff260-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="ff260-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ff260-107">**Column**</span></span>|<span data-ttu-id="ff260-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ff260-108">**Data Type**</span></span>|<span data-ttu-id="ff260-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ff260-109">**Key/Index**</span></span>|<span data-ttu-id="ff260-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ff260-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff260-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ff260-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ff260-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ff260-112">datetime</span></span>  <br/> |<span data-ttu-id="ff260-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ff260-113">Primary</span></span>  <br/> |<span data-ttu-id="ff260-114">Zeitstempel, intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff260-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="ff260-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="ff260-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="ff260-116">int</span><span class="sxs-lookup"><span data-stu-id="ff260-116">int</span></span>  <br/> |<span data-ttu-id="ff260-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ff260-117">Primary</span></span>  <br/> |<span data-ttu-id="ff260-118">Eindeutige Nummer, die diesen Konferenz-URI kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ff260-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="ff260-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="ff260-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="ff260-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ff260-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="ff260-121">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="ff260-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="ff260-122">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="ff260-122">**Checksum**</span></span> <br/> |<span data-ttu-id="ff260-123">int</span><span class="sxs-lookup"><span data-stu-id="ff260-123">int</span></span>  <br/> ||<span data-ttu-id="ff260-124">Prüfsumme von ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="ff260-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="ff260-125">Wird verwendet, um die Geschwindigkeit von Datenbanksuchen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ff260-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="ff260-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="ff260-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="ff260-127">int</span><span class="sxs-lookup"><span data-stu-id="ff260-127">int</span></span>  <br/> |<span data-ttu-id="ff260-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="ff260-128">Foreign</span></span>  <br/> |<span data-ttu-id="ff260-129">URI-Typ wie conf: Chat für im-Konferenz oder conf: Audio-Video für Audio/Video-Konferenz.</span><span class="sxs-lookup"><span data-stu-id="ff260-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="ff260-130">Weitere Informationen finden Sie in der [Tabelle UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="ff260-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

