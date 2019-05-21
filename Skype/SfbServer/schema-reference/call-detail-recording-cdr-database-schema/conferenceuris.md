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
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296392"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="07e23-104">ConferenceUris-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="07e23-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07e23-105">Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="07e23-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="07e23-106">Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="07e23-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="07e23-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="07e23-107">**Column**</span></span>|<span data-ttu-id="07e23-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="07e23-108">**Data Type**</span></span>|<span data-ttu-id="07e23-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="07e23-109">**Key/Index**</span></span>|<span data-ttu-id="07e23-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="07e23-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07e23-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="07e23-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="07e23-112">datetime</span><span class="sxs-lookup"><span data-stu-id="07e23-112">datetime</span></span>  <br/> |<span data-ttu-id="07e23-113">Primary</span><span class="sxs-lookup"><span data-stu-id="07e23-113">Primary</span></span>  <br/> |<span data-ttu-id="07e23-114">Zeitstempel, intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="07e23-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="07e23-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="07e23-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="07e23-116">int</span><span class="sxs-lookup"><span data-stu-id="07e23-116">int</span></span>  <br/> |<span data-ttu-id="07e23-117">Primary</span><span class="sxs-lookup"><span data-stu-id="07e23-117">Primary</span></span>  <br/> |<span data-ttu-id="07e23-118">Eindeutige Nummer, die diesen Konferenz-URI kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="07e23-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="07e23-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="07e23-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="07e23-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="07e23-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="07e23-121">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="07e23-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="07e23-122">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="07e23-122">**Checksum**</span></span> <br/> |<span data-ttu-id="07e23-123">int</span><span class="sxs-lookup"><span data-stu-id="07e23-123">int</span></span>  <br/> ||<span data-ttu-id="07e23-124">Prüfsumme von ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="07e23-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="07e23-125">Wird verwendet, um die Geschwindigkeit von Datenbanksuchen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="07e23-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="07e23-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="07e23-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="07e23-127">int</span><span class="sxs-lookup"><span data-stu-id="07e23-127">int</span></span>  <br/> |<span data-ttu-id="07e23-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="07e23-128">Foreign</span></span>  <br/> |<span data-ttu-id="07e23-129">URI-Typ wie conf: Chat für im-Konferenz oder conf: Audio-Video für Audio/Video-Konferenz.</span><span class="sxs-lookup"><span data-stu-id="07e23-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="07e23-130">Weitere Informationen finden Sie in der [Tabelle UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="07e23-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

