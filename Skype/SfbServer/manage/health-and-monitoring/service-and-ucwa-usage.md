---
title: Überwachen des mobilitätsdiensts und der UCWA-Nutzung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten des mobilitätsdiensts (MCX) und der Unified Communications Web-API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817684"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="afd90-103">Überwachen des mobilitätsdiensts und der UCWA-Nutzung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="afd90-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="afd90-104">**Zusammenfassung:** Verwalten Sie den Mobilitätsdienst (MCX) und die Unified Communications Web-API (UCWA) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="afd90-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="afd90-105">MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="afd90-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="afd90-106">Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="afd90-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="afd90-107">Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.</span><span class="sxs-lookup"><span data-stu-id="afd90-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="afd90-108">Auf einer kontinuierlichen Basis sollten Sie die CPU und den Arbeitsspeicher überwachen, die von Skype for Business Server Mobility Service (MCX) und der Unified Communications Web-API (UCWA) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afd90-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="afd90-109">Zum Überwachen der Auslastung können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="afd90-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="afd90-110">**Für die Unified Communications-Web-API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="afd90-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="afd90-111">Der **LyncUcwa** -Workerprozess im Internet Informationsdienste (IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="afd90-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="afd90-112">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="afd90-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="afd90-113">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="afd90-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="afd90-114">Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="afd90-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="afd90-115">Die Speicherauslastung sollte innerhalb der in Skype for Business Server festgelegten Grenzwerte unter [Monitor für Server Speicherkapazität](server-memory-capacity-limits.md)liegen.</span><span class="sxs-lookup"><span data-stu-id="afd90-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="afd90-116">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="afd90-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="afd90-117">**Ls: webdrosselungs-und Authentication\WEB Gesamtanforderungen in der Verarbeitung**, die die Anzahl der ausstehenden Webanforderungen auf dem Server angeben.</span><span class="sxs-lookup"><span data-stu-id="afd90-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="afd90-118">Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="afd90-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="afd90-119">**ASP.NET\Requests Queued** (sollte immer Null sein).</span><span class="sxs-lookup"><span data-stu-id="afd90-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="afd90-120">Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="afd90-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="afd90-121">**Für den Mobilitätsdienst (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="afd90-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="afd90-122">Die **CSIntMcxAppPool** -und **CSExtMcxAppPool** -Arbeitsprozesse im Internet Informationsdienste (IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="afd90-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="afd90-123">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="afd90-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="afd90-124">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="afd90-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="afd90-125">Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="afd90-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="afd90-126">Die Speicherauslastung sollte innerhalb der in Skype for Business Server festgelegten Grenzwerte unter [Monitor für Server Speicherkapazität](server-memory-capacity-limits.md)liegen.</span><span class="sxs-lookup"><span data-stu-id="afd90-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="afd90-127">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="afd90-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="afd90-128">**ASP.NET v2.0.50727\Requests Current**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt.</span><span class="sxs-lookup"><span data-stu-id="afd90-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="afd90-129">Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="afd90-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="afd90-130">**ASP.NET\Requests Queued** (sollte immer Null sein).</span><span class="sxs-lookup"><span data-stu-id="afd90-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="afd90-131">Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="afd90-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="afd90-132">MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="afd90-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="afd90-133">Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="afd90-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="afd90-134">Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.</span><span class="sxs-lookup"><span data-stu-id="afd90-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="afd90-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afd90-135">See also</span></span>

[<span data-ttu-id="afd90-136">Überwachen der Kapazitätsgrenzen von Server Speicher in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="afd90-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
