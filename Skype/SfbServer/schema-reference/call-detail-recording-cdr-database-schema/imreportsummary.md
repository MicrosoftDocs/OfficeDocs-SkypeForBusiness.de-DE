---
title: IMReportSummary-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Die IMReportSummaryTable stellt einen Gesamtbericht auf die chatsitzungen in einer Organisation bereit. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213032"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="09031-104">IMReportSummary-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09031-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="09031-105">Die IMReportSummaryTable stellt einen Gesamtbericht auf die chatsitzungen in einer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="09031-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="09031-106">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="09031-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="09031-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="09031-107">**Column**</span></span>|<span data-ttu-id="09031-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="09031-108">**Data Type**</span></span>|<span data-ttu-id="09031-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="09031-109">**Key/Index**</span></span>|<span data-ttu-id="09031-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="09031-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09031-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="09031-111">**StartTime**</span></span> <br/> |<span data-ttu-id="09031-112">datetime</span><span class="sxs-lookup"><span data-stu-id="09031-112">datetime</span></span>  <br/> |<span data-ttu-id="09031-113">Primary</span><span class="sxs-lookup"><span data-stu-id="09031-113">Primary</span></span>  <br/> |<span data-ttu-id="09031-114">Datum und Uhrzeit des Beginns die instant messaging-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="09031-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="09031-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="09031-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="09031-116">vom Datentyp char(1)</span><span class="sxs-lookup"><span data-stu-id="09031-116">char(1)</span></span>  <br/> |<span data-ttu-id="09031-117">Primary</span><span class="sxs-lookup"><span data-stu-id="09031-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="09031-118">**"Poolfqdn"**</span><span class="sxs-lookup"><span data-stu-id="09031-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="09031-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="09031-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="09031-120">Primary</span><span class="sxs-lookup"><span data-stu-id="09031-120">Primary</span></span>  <br/> |<span data-ttu-id="09031-121">Vollqualifizierter Domänenname des Pools, der die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="09031-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="09031-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="09031-122">**AuthType**</span></span> <br/> |<span data-ttu-id="09031-123">int</span><span class="sxs-lookup"><span data-stu-id="09031-123">int</span></span>  <br/> |<span data-ttu-id="09031-124">Primary</span><span class="sxs-lookup"><span data-stu-id="09031-124">Primary</span></span>  <br/> |<span data-ttu-id="09031-125">Priorität (beispielsweise dringend oder nicht dringend) des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="09031-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="09031-126">Prioritätsinformationen werden in der [CallPriorities-Tabelle in Skype für Business Server 2015](callpriorities.md)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="09031-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="09031-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="09031-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="09031-128">bigint</span><span class="sxs-lookup"><span data-stu-id="09031-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="09031-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="09031-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="09031-130">bigint</span><span class="sxs-lookup"><span data-stu-id="09031-130">bigint</span></span>  <br/> ||<span data-ttu-id="09031-131">Gesamtzahl der Sofortnachrichten, die während der Sitzung ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="09031-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

