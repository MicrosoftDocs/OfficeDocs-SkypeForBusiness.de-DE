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
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296126"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b8cb7-104">IMReportSummary-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b8cb7-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b8cb7-105">Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden.</span><span class="sxs-lookup"><span data-stu-id="b8cb7-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="b8cb7-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b8cb7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b8cb7-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-107">**Column**</span></span>|<span data-ttu-id="b8cb7-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-108">**Data Type**</span></span>|<span data-ttu-id="b8cb7-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-109">**Key/Index**</span></span>|<span data-ttu-id="b8cb7-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8cb7-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-111">**StartTime**</span></span> <br/> |<span data-ttu-id="b8cb7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b8cb7-112">datetime</span></span>  <br/> |<span data-ttu-id="b8cb7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b8cb7-113">Primary</span></span>  <br/> |<span data-ttu-id="b8cb7-114">Das Datum und die Uhrzeit, zu der die Sofortnachrichtensitzung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="b8cb7-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="b8cb7-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="b8cb7-116">Zeichen (1)</span><span class="sxs-lookup"><span data-stu-id="b8cb7-116">char(1)</span></span>  <br/> |<span data-ttu-id="b8cb7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="b8cb7-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="b8cb7-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="b8cb7-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="b8cb7-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="b8cb7-120">Primary</span><span class="sxs-lookup"><span data-stu-id="b8cb7-120">Primary</span></span>  <br/> |<span data-ttu-id="b8cb7-121">Vollständig qualifizierter Domänenname des Pools, der die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="b8cb7-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="b8cb7-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-122">**AuthType**</span></span> <br/> |<span data-ttu-id="b8cb7-123">int</span><span class="sxs-lookup"><span data-stu-id="b8cb7-123">int</span></span>  <br/> |<span data-ttu-id="b8cb7-124">Primary</span><span class="sxs-lookup"><span data-stu-id="b8cb7-124">Primary</span></span>  <br/> |<span data-ttu-id="b8cb7-125">Priorität (beispielsweise dringende oder nicht dringende) des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="b8cb7-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="b8cb7-126">Prioritätsinformationen werden in der [CallPriorities-Tabelle in Skype for Business Server 2015](callpriorities.md)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b8cb7-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="b8cb7-127">**SessionCount gespeichert**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="b8cb7-128">bigint</span><span class="sxs-lookup"><span data-stu-id="b8cb7-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="b8cb7-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="b8cb7-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="b8cb7-130">bigint</span><span class="sxs-lookup"><span data-stu-id="b8cb7-130">bigint</span></span>  <br/> ||<span data-ttu-id="b8cb7-131">Die Gesamtzahl der während der Sitzung ausgetauschten Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="b8cb7-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

