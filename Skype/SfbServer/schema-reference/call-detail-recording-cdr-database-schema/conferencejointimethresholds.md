---
title: ConferenceJoinTimeThresholds-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Die Tabelle conferencejointimethresholds enthält die klassifizierungsgrenzen, die von der Konferenz beitreten Zeit Summary Report verwendet. Die Zusammenfassung der Konferenzbeitrittszeit enthält eine Zusammenfassung den Betrag Zeitaufwand für Benutzer erfolgreich eine Konferenz beitreten; Diese Zeitwerte werden sowohl als durchschnittlich und in einem der folgenden Kategorien gemeldet:'
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901436"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cbfcb-104">ConferenceJoinTimeThresholds-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cbfcb-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cbfcb-105">Die Tabelle conferencejointimethresholds enthält die klassifizierungsgrenzen, die von der Konferenz beitreten Zeit Summary Report verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="cbfcb-106">Die Zusammenfassung der Konferenzbeitrittszeit enthält eine Zusammenfassung den Betrag Zeitaufwand für Benutzer erfolgreich eine Konferenz beitreten; Diese Zeitwerte werden sowohl als durchschnittlich und in einem der folgenden Kategorien gemeldet:</span><span class="sxs-lookup"><span data-stu-id="cbfcb-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="cbfcb-107">Weniger als 2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="cbfcb-108">Zwischen 2 Sekunden und 5 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="cbfcb-109">Zwischen 5 und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="cbfcb-110">Mehr als 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="cbfcb-111">Die Tabelle conferencejointimethresholds enthält die klassifizierungswerte 2 Sekunden, 5 Sekunden und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="cbfcb-112">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cbfcb-113">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cbfcb-113">**Column**</span></span>|<span data-ttu-id="cbfcb-114">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="cbfcb-114">**Data Type**</span></span>|<span data-ttu-id="cbfcb-115">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="cbfcb-115">**Key/Index**</span></span>|<span data-ttu-id="cbfcb-116">**Details**</span><span class="sxs-lookup"><span data-stu-id="cbfcb-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbfcb-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="cbfcb-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="cbfcb-118">int</span><span class="sxs-lookup"><span data-stu-id="cbfcb-118">int</span></span>  <br/> |<span data-ttu-id="cbfcb-119">Primary</span><span class="sxs-lookup"><span data-stu-id="cbfcb-119">Primary</span></span>  <br/> |<span data-ttu-id="cbfcb-120">Eindeutiger Bezeichner für die Klassifikation.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="cbfcb-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="cbfcb-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="cbfcb-122">int</span><span class="sxs-lookup"><span data-stu-id="cbfcb-122">int</span></span>  <br/> || <span data-ttu-id="cbfcb-123">Die Obergrenze für die Klassifikation.</span><span class="sxs-lookup"><span data-stu-id="cbfcb-123">Upper limit for the classification.</span></span> <span data-ttu-id="cbfcb-124">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="cbfcb-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="cbfcb-125">2</span><span class="sxs-lookup"><span data-stu-id="cbfcb-125">2</span></span> <br/>  <span data-ttu-id="cbfcb-126">5</span><span class="sxs-lookup"><span data-stu-id="cbfcb-126">5</span></span> <br/>  <span data-ttu-id="cbfcb-127">10</span><span class="sxs-lookup"><span data-stu-id="cbfcb-127">10</span></span> <br/> |
   

