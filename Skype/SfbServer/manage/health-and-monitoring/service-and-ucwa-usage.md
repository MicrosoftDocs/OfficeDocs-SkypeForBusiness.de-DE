---
title: Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten der Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.'
ms.openlocfilehash: 79516ec6cf5371061a0287e70e6ed81f8b2a5395
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197499"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="d01e0-103">Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d01e0-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="d01e0-104">**Zusammenfassung:** Verwalten Sie der Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="d01e0-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="d01e0-105">Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d01e0-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d01e0-106">Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden.</span><span class="sxs-lookup"><span data-stu-id="d01e0-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d01e0-107">Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d01e0-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="d01e0-108">Kontinuierlich sollten Sie überwachen, CPU und Arbeitsspeicher, die von der Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d01e0-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="d01e0-109">Zum Überwachen der Auslastung können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="d01e0-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="d01e0-110">**Für die Unified Communications-Web-API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="d01e0-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="d01e0-111">Der **LyncUcwa** -Arbeitsprozess in Internetinformationsdienste (Internet Information Services, IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="d01e0-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="d01e0-112">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="d01e0-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="d01e0-113">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="d01e0-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="d01e0-114">Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="d01e0-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="d01e0-115">Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.</span><span class="sxs-lookup"><span data-stu-id="d01e0-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="d01e0-116">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="d01e0-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="d01e0-117">**LS:WEB - Drosselung und Authentication\WEB - Gesamtanfragen bei der Verarbeitung**, gibt die Anzahl der ausstehenden Webanfragen auf dem Server an.</span><span class="sxs-lookup"><span data-stu-id="d01e0-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="d01e0-118">Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="d01e0-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="d01e0-119">**ASP.NET\Requests Queued** (sollte immer Null sein).</span><span class="sxs-lookup"><span data-stu-id="d01e0-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d01e0-120">Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="d01e0-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="d01e0-121">**Für den Mobilitätsdienst (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="d01e0-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="d01e0-122">Die **CSIntMcxAppPool** und **CSExtMcxAppPool** Arbeitsprozesse in Internetinformationsdienste (Internet Information Services, IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="d01e0-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="d01e0-123">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="d01e0-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="d01e0-124">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="d01e0-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="d01e0-125">Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="d01e0-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="d01e0-126">Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.</span><span class="sxs-lookup"><span data-stu-id="d01e0-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="d01e0-127">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="d01e0-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="d01e0-128">**ASP.NET v2.0.50727\Requests Current**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt.</span><span class="sxs-lookup"><span data-stu-id="d01e0-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="d01e0-129">Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="d01e0-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="d01e0-130">**ASP.NET\Requests Queued** (sollte immer Null sein).</span><span class="sxs-lookup"><span data-stu-id="d01e0-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d01e0-131">Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="d01e0-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="d01e0-132">Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d01e0-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d01e0-133">Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden.</span><span class="sxs-lookup"><span data-stu-id="d01e0-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d01e0-134">Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d01e0-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d01e0-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d01e0-135">See also</span></span>

[<span data-ttu-id="d01e0-136">Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d01e0-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
