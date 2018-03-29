---
title: Media-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Die Medienansicht speichert Informationen über einen Medientyp in einer Peer-zu-Peer-Sitzung verwendet. Eine Sitzung würde durch mehrere Datensätze in der Tabelle dargestellt werden, wenn mehr als eine Medientyp verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a><span data-ttu-id="ef6b7-105">Media-Ansicht</span><span class="sxs-lookup"><span data-stu-id="ef6b7-105">Media view</span></span>
 
<span data-ttu-id="ef6b7-106">Die Medienansicht speichert Informationen über einen Medientyp in einer Peer-zu-Peer-Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="ef6b7-107">Eine Sitzung würde durch mehrere Datensätze in der Tabelle dargestellt werden, wenn mehr als eine Medientyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="ef6b7-108">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef6b7-109">Die Medienansicht sollte nicht verwendet werden, um die Dauer Medien für eine Sitzung berechnen.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="ef6b7-110">Diese Ansicht enthält die Signalisierung Details der Austausch von Mediendaten in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="ef6b7-111">Austausch von Mediendaten erfolgt durch die INVITE-Anforderung und StartTime gibt die Zeit an, der die INVITE-Nachricht gesendet wurde. Die Zeit einladen bedeutet nicht unbedingt, dass das Medium Startzeit, da Media gestartet wird, nachdem die Sitzung akzeptiert wird.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="ef6b7-112">Die Medienansicht enthält alle Spalten in der [SessionDetails View](sessiondetails-0.md) außerdem die unten aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="ef6b7-113">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ef6b7-113">**Column**</span></span>|<span data-ttu-id="ef6b7-114">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ef6b7-114">**Data Type**</span></span>|<span data-ttu-id="ef6b7-115">**Details**</span><span class="sxs-lookup"><span data-stu-id="ef6b7-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ef6b7-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="ef6b7-116">**Media**</span></span> <br/> |<span data-ttu-id="ef6b7-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ef6b7-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef6b7-118">Medientyp.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-118">Media type.</span></span> <span data-ttu-id="ef6b7-119">Finden Sie weitere Informationen die [MediaList-Tabelle](medialist.md) .</span><span class="sxs-lookup"><span data-stu-id="ef6b7-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ef6b7-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="ef6b7-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="ef6b7-121">datetime</span><span class="sxs-lookup"><span data-stu-id="ef6b7-121">datetime</span></span>  <br/> |<span data-ttu-id="ef6b7-122">Uhrzeit, zu der eine medienanforderung gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="ef6b7-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="ef6b7-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="ef6b7-124">datetime</span><span class="sxs-lookup"><span data-stu-id="ef6b7-124">datetime</span></span>  <br/> |<span data-ttu-id="ef6b7-125">Die Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ef6b7-125">End time of the session.</span></span>  <br/> |
   

