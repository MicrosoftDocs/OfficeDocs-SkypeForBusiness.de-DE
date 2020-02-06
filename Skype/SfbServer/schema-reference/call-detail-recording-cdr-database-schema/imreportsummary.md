---
title: IMReportSummary-Tabelle in Skype for Business Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815143"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="51ba0-104">IMReportSummary-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="51ba0-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="51ba0-105">Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden.</span><span class="sxs-lookup"><span data-stu-id="51ba0-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="51ba0-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="51ba0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="51ba0-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="51ba0-107">**Column**</span></span>|<span data-ttu-id="51ba0-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="51ba0-108">**Data Type**</span></span>|<span data-ttu-id="51ba0-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="51ba0-109">**Key/Index**</span></span>|<span data-ttu-id="51ba0-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="51ba0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="51ba0-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="51ba0-111">**StartTime**</span></span> <br/> |<span data-ttu-id="51ba0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="51ba0-112">datetime</span></span>  <br/> |<span data-ttu-id="51ba0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="51ba0-113">Primary</span></span>  <br/> |<span data-ttu-id="51ba0-114">Das Datum und die Uhrzeit, zu der die Sofortnachrichtensitzung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="51ba0-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="51ba0-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="51ba0-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="51ba0-116">Zeichen (1)</span><span class="sxs-lookup"><span data-stu-id="51ba0-116">char(1)</span></span>  <br/> |<span data-ttu-id="51ba0-117">Primary</span><span class="sxs-lookup"><span data-stu-id="51ba0-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="51ba0-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="51ba0-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="51ba0-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="51ba0-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="51ba0-120">Primary</span><span class="sxs-lookup"><span data-stu-id="51ba0-120">Primary</span></span>  <br/> |<span data-ttu-id="51ba0-121">Vollständig qualifizierter Domänenname des Pools, der die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="51ba0-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="51ba0-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="51ba0-122">**AuthType**</span></span> <br/> |<span data-ttu-id="51ba0-123">int</span><span class="sxs-lookup"><span data-stu-id="51ba0-123">int</span></span>  <br/> |<span data-ttu-id="51ba0-124">Primary</span><span class="sxs-lookup"><span data-stu-id="51ba0-124">Primary</span></span>  <br/> |<span data-ttu-id="51ba0-125">Priorität (beispielsweise dringende oder nicht dringende) des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51ba0-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="51ba0-126">Prioritätsinformationen werden in der [CallPriorities-Tabelle in Skype for Business Server 2015](callpriorities.md)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="51ba0-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="51ba0-127">**SessionCount gespeichert**</span><span class="sxs-lookup"><span data-stu-id="51ba0-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="51ba0-128">bigint</span><span class="sxs-lookup"><span data-stu-id="51ba0-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="51ba0-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="51ba0-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="51ba0-130">bigint</span><span class="sxs-lookup"><span data-stu-id="51ba0-130">bigint</span></span>  <br/> ||<span data-ttu-id="51ba0-131">Die Gesamtzahl der während der Sitzung ausgetauschten Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="51ba0-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

