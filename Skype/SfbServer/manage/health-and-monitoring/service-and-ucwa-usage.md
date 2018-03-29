---
title: Überwachen des Mobilitätsdienstes und der Verwendung der UCWA in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten von den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications in Skype für Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a><span data-ttu-id="3c755-103">Überwachen des Mobilitätsdienstes und der Verwendung der UCWA in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c755-103">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3c755-104">**Zusammenfassung:** Verwalten Sie den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3c755-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3c755-105">Kontinuierlich sollten Sie überwachen, CPU und Arbeitsspeicher, die von der Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c755-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="3c755-106">Zum Überwachen der Auslastung können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c755-106">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="3c755-107">**Für die Unified Communications-Web-API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="3c755-107">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="3c755-108">Der **LyncUcwa** -Arbeitsprozess in Internetinformationsdienste (Internet Information Services, IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="3c755-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="3c755-109">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="3c755-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="3c755-110">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="3c755-110">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="3c755-111">Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="3c755-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="3c755-112">Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server 2015](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.</span><span class="sxs-lookup"><span data-stu-id="3c755-112">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="3c755-113">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="3c755-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="3c755-114">**LS:WEB - Drosselung und Authentication\WEB - Gesamtanfragen bei der Verarbeitung**, gibt die Anzahl der ausstehenden Webanfragen auf dem Server an.</span><span class="sxs-lookup"><span data-stu-id="3c755-114">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="3c755-115">Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="3c755-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="3c755-116">**ASP.NET\Requests Queued** (sollte immer NULL sein).</span><span class="sxs-lookup"><span data-stu-id="3c755-116">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3c755-117">Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="3c755-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="3c755-118">**Für den Mobilitätsdienst (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="3c755-118">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="3c755-119">Die **CSIntMcxAppPool** und **CSExtMcxAppPool** Arbeitsprozesse in Internetinformationsdienste (Internet Information Services, IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="3c755-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="3c755-120">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="3c755-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="3c755-121">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="3c755-121">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="3c755-122">Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="3c755-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="3c755-123">Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server 2015](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.</span><span class="sxs-lookup"><span data-stu-id="3c755-123">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="3c755-124">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="3c755-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="3c755-125">**ASP.NET v2.0.50727\Requests aktuelle**, gibt die Anzahl der ausstehenden Webanfragen auf dem Server an.</span><span class="sxs-lookup"><span data-stu-id="3c755-125">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="3c755-126">Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="3c755-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="3c755-127">**ASP.NET\Requests Queued** (sollte immer NULL sein).</span><span class="sxs-lookup"><span data-stu-id="3c755-127">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3c755-128">Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="3c755-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3c755-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c755-129">See also</span></span>

#### 

[<span data-ttu-id="3c755-130">Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c755-130">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)

