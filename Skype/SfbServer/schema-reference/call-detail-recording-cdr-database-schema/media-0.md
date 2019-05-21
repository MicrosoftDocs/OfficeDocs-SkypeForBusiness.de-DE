---
title: Medienansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: In der Medienansicht werden Informationen zu einem Medientyp gespeichert, der in einer Peer-to-Peer-Sitzung verwendet wird. Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296000"
---
# <a name="media-view"></a><span data-ttu-id="adeea-105">Medienansicht</span><span class="sxs-lookup"><span data-stu-id="adeea-105">Media view</span></span>
 
<span data-ttu-id="adeea-106">In der Medienansicht werden Informationen zu einem Medientyp gespeichert, der in einer Peer-to-Peer-Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="adeea-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="adeea-107">Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="adeea-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="adeea-108">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="adeea-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adeea-109">Die Medienansicht sollte nicht verwendet werden, um die Mediendauer einer Sitzung zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="adeea-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="adeea-110">Diese Ansicht enthält die Signalisierungs Details von Medienaustausch in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="adeea-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="adeea-111">Der Medienaustausch erfolgt über die Einladungs Anfrage, und Startzeit gibt an, wie lange die Einladung gesendet wurde. Die Einladungs Zeit bedeutet nicht unbedingt die Startzeit des Mediums, da Medien erst nach Annahme der Sitzung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="adeea-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="adeea-112">Die Medienansicht enthält alle Spalten in der SessionDetails- [Ansicht](sessiondetails-0.md) sowie die nachstehend aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="adeea-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="adeea-113">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="adeea-113">**Column**</span></span>|<span data-ttu-id="adeea-114">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="adeea-114">**Data Type**</span></span>|<span data-ttu-id="adeea-115">**Details**</span><span class="sxs-lookup"><span data-stu-id="adeea-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="adeea-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="adeea-116">**Media**</span></span> <br/> |<span data-ttu-id="adeea-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="adeea-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="adeea-118">Medientyp.</span><span class="sxs-lookup"><span data-stu-id="adeea-118">Media type.</span></span> <span data-ttu-id="adeea-119">Weitere Informationen finden Sie in der [Tabelle medialist](medialist.md) .</span><span class="sxs-lookup"><span data-stu-id="adeea-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="adeea-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="adeea-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="adeea-121">datetime</span><span class="sxs-lookup"><span data-stu-id="adeea-121">datetime</span></span>  <br/> |<span data-ttu-id="adeea-122">Zeit, zu der eine Medienanfrage gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="adeea-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="adeea-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="adeea-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="adeea-124">datetime</span><span class="sxs-lookup"><span data-stu-id="adeea-124">datetime</span></span>  <br/> |<span data-ttu-id="adeea-125">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="adeea-125">End time of the session.</span></span>  <br/> |
   

