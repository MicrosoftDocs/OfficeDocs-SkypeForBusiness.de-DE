---
title: ConferenceJoinTimeThresholds-Tabelle in Skype for Business Server 2015
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Die Tabelle "ConferenceJoinTimeThresholds" enthält die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht "Konferenzteilnahme Zeit" verwendet werden. Der Bericht "Konferenz Teilzeit-Zusammenfassung" fasst die Zeitspanne zusammen, die der Benutzer für eine erfolgreiche Teilnahme an einer Konferenz benötigt. Diese Zeitwerte werden sowohl als Mittelwert als auch in einer der folgenden Kategorien angezeigt:'
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815393"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4edfc-104">ConferenceJoinTimeThresholds-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4edfc-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4edfc-105">Die Tabelle "ConferenceJoinTimeThresholds" enthält die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht "Konferenzteilnahme Zeit" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4edfc-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="4edfc-106">Der Bericht "Konferenz Teilzeit-Zusammenfassung" fasst die Zeitspanne zusammen, die der Benutzer für eine erfolgreiche Teilnahme an einer Konferenz benötigt. Diese Zeitwerte werden sowohl als Mittelwert als auch in einer der folgenden Kategorien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4edfc-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="4edfc-107">Weniger als 2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="4edfc-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="4edfc-108">Zwischen 2 Sekunden und 5 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="4edfc-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="4edfc-109">Zwischen 5 Sekunden und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="4edfc-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="4edfc-110">Mehr als 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="4edfc-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="4edfc-111">Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungs Werte 2 Sekunden, 5 Sekunden und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="4edfc-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="4edfc-112">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4edfc-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4edfc-113">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4edfc-113">**Column**</span></span>|<span data-ttu-id="4edfc-114">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="4edfc-114">**Data Type**</span></span>|<span data-ttu-id="4edfc-115">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="4edfc-115">**Key/Index**</span></span>|<span data-ttu-id="4edfc-116">**Details**</span><span class="sxs-lookup"><span data-stu-id="4edfc-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4edfc-117">**Schwellenwert**</span><span class="sxs-lookup"><span data-stu-id="4edfc-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="4edfc-118">int</span><span class="sxs-lookup"><span data-stu-id="4edfc-118">int</span></span>  <br/> |<span data-ttu-id="4edfc-119">Primary</span><span class="sxs-lookup"><span data-stu-id="4edfc-119">Primary</span></span>  <br/> |<span data-ttu-id="4edfc-120">Eindeutiger Bezeichner für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="4edfc-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="4edfc-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="4edfc-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="4edfc-122">int</span><span class="sxs-lookup"><span data-stu-id="4edfc-122">int</span></span>  <br/> || <span data-ttu-id="4edfc-123">Obergrenze für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="4edfc-123">Upper limit for the classification.</span></span> <span data-ttu-id="4edfc-124">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4edfc-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="4edfc-125">2</span><span class="sxs-lookup"><span data-stu-id="4edfc-125">2</span></span> <br/>  <span data-ttu-id="4edfc-126">5</span><span class="sxs-lookup"><span data-stu-id="4edfc-126">5</span></span> <br/>  <span data-ttu-id="4edfc-127">10</span><span class="sxs-lookup"><span data-stu-id="4edfc-127">10</span></span> <br/> |
   

