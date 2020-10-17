---
title: 'Lync Server 2013: Überwachen des mobilitätsdiensts und der UCWA-Verwendung'
description: 'Lync Server 2013: Überwachung des mobilitätsdiensts und der UCWA-Nutzung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6575941faf904e46cd1f66d7226a16c88e8cbaa3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548111"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="bed87-103">Überwachen des mobilitätsdiensts und der UCWA Verwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed87-103">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed87-104">_**Letztes Änderungsstand des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="bed87-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="bed87-105">Auf einer kontinuierlichen Basis sollten Sie die CPU und den Arbeitsspeicher überwachen, die vom lync Server Mobilitätsdienst (MCX) und dem Unified Communications Web API (UCWA) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bed87-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="bed87-106">Zum Überwachen der Verwendung können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="bed87-106">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="bed87-107">**Für Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="bed87-107">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="bed87-108">Der **LyncUcwa** -Arbeitsprozess in Internet Information Services (IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="bed87-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="bed87-109">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="bed87-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="bed87-110">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="bed87-110">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="bed87-111">Für die meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="bed87-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="bed87-112">Die Arbeitsspeicherauslastung sollte innerhalb der unter [Monitoring for Server Memory Capacity Limits in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)beschriebenen Grenzen liegen.</span><span class="sxs-lookup"><span data-stu-id="bed87-112">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="bed87-113">Zusätzlich zu den Leistungsindikatoren für CPU-und Speicherauslastung können Sie die folgenden Leistungsindikatoren verwenden, um zu ermitteln, wann ein Server mit Anforderungen überladen ist:</span><span class="sxs-lookup"><span data-stu-id="bed87-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="bed87-114">**Ls: Internet – Drosselung und Authentifizierung \\ "Gesamt"-Anforderungen in der Verarbeitung**, die die Anzahl der ausstehenden Webanforderungen auf dem Server angibt.</span><span class="sxs-lookup"><span data-stu-id="bed87-114">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="bed87-115">Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung "503-Dienst ist nicht verfügbar" fehl.</span><span class="sxs-lookup"><span data-stu-id="bed87-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="bed87-116">**ASP.net \\ Anforderungen in der Warteschlange** (sollte immer NULL sein).</span><span class="sxs-lookup"><span data-stu-id="bed87-116">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bed87-117">Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie die Kapazitätsplanung für die richtige Größe der CPU, die Anzahl der Prozessorkerne und den Arbeitsspeicher für die Computer, die die Webdienste hosten, erneut überarbeiten und neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="bed87-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="bed87-118">**Für den Mobilitätsdienst (MCX):**</span><span class="sxs-lookup"><span data-stu-id="bed87-118">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="bed87-119">Die **CSIntMcxAppPool** -und **CSExtMcxAppPool** -Arbeitsprozesse in Internet Information Services (IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="bed87-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="bed87-120">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="bed87-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="bed87-121">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="bed87-121">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="bed87-122">Für die meisten Bereitstellungen sollte die CPU-Auslastung des mobilitätsdiensts im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="bed87-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="bed87-123">Die Arbeitsspeicherauslastung sollte innerhalb der unter [Monitoring for Server Memory Capacity Limits in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)beschriebenen Grenzen liegen.</span><span class="sxs-lookup"><span data-stu-id="bed87-123">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="bed87-124">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="bed87-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="bed87-125">**ASP.NET v 2.0.50727 \\ Fordert Current**an und gibt die Anzahl der ausstehenden Webanforderungen auf dem Server an.</span><span class="sxs-lookup"><span data-stu-id="bed87-125">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="bed87-126">Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung "503-Dienst ist nicht verfügbar" fehl.</span><span class="sxs-lookup"><span data-stu-id="bed87-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="bed87-127">**ASP.net \\ Anforderungen in der Warteschlange** (sollte immer NULL sein).</span><span class="sxs-lookup"><span data-stu-id="bed87-127">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bed87-128">Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie die Kapazitätsplanung für die richtige Größe der CPU, die Anzahl der Prozessorkerne und den Arbeitsspeicher für die Computer, die die Webdienste hosten, erneut überarbeiten und neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="bed87-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bed87-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bed87-129">See Also</span></span>


[<span data-ttu-id="bed87-130">Überwachen der Kapazitätsgrenzwerte für Server Speicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed87-130">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

