---
title: 'Lync Server 2013: Überwachen des mobilitätsdiensts und der UCWA-Verwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="3974e-102">Überwachen des mobilitätsdiensts und der UCWA-Verwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3974e-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3974e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="3974e-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="3974e-104">Auf einer kontinuierlichen Basis sollten Sie die CPU und den Arbeitsspeicher überwachen, die vom lync Server Mobility Service (MCX) und der Unified Communications Web-API (UCWA) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3974e-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="3974e-105">Zum Überwachen der Auslastung können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="3974e-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="3974e-106">**Für die Unified Communications-Web-API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="3974e-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="3974e-107">Der **LyncUcwa** -Workerprozess im Internet Informationsdienste (IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="3974e-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="3974e-108">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="3974e-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="3974e-109">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="3974e-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="3974e-110">Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="3974e-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="3974e-111">Die Speicherauslastung sollte innerhalb der Grenzwerte liegen, die unter [Überwachen der Speicher Kapazitätsgrenzwerte von Servern in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3974e-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="3974e-112">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="3974e-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="3974e-113">**Ls: Web – Drosselungs-und\\Authentifizierungs Web – Gesamtanforderungen in der Verarbeitung**, die die Anzahl der ausstehenden Webanforderungen auf dem Server angeben.</span><span class="sxs-lookup"><span data-stu-id="3974e-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="3974e-114">Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="3974e-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="3974e-115">**ASP.net\\-Anforderungen in der Warteschlange** (sollte immer 0 sein).</span><span class="sxs-lookup"><span data-stu-id="3974e-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3974e-116">Wenn Sie diese Werte erfüllen oder übertreffen, sollten Sie Ihre Kapazitätsplanung erneut überarbeiten und neu berechnen, um die korrekte Größe der CPU, die Anzahl der Kerne und den Arbeitsspeicher für die Computer zu ermitteln, die die Webdienste hosten.</span><span class="sxs-lookup"><span data-stu-id="3974e-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="3974e-117">**Für den Mobilitätsdienst (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="3974e-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="3974e-118">Die **CSIntMcxAppPool** -und **CSExtMcxAppPool** -Arbeitsprozesse im Internet Informationsdienste (IIS)-Manager.</span><span class="sxs-lookup"><span data-stu-id="3974e-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="3974e-119">Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.</span><span class="sxs-lookup"><span data-stu-id="3974e-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="3974e-120">Die Leistungsindikatoren **CPU** und **Prozessor**.</span><span class="sxs-lookup"><span data-stu-id="3974e-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="3974e-121">Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen.</span><span class="sxs-lookup"><span data-stu-id="3974e-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="3974e-122">Die Speicherauslastung sollte innerhalb der Grenzwerte liegen, die unter [Überwachen der Speicher Kapazitätsgrenzwerte von Servern in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3974e-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="3974e-123">Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:</span><span class="sxs-lookup"><span data-stu-id="3974e-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="3974e-124">**ASP.NET v 2.0.50727\\fordert Current**auf, wodurch die Anzahl ausstehender Webanforderungen auf dem Server angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3974e-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="3974e-125">Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.</span><span class="sxs-lookup"><span data-stu-id="3974e-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="3974e-126">**ASP.net\\-Anforderungen in der Warteschlange** (sollte immer 0 sein).</span><span class="sxs-lookup"><span data-stu-id="3974e-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3974e-127">Wenn Sie diese Werte erfüllen oder übertreffen, sollten Sie Ihre Kapazitätsplanung erneut überarbeiten und neu berechnen, um die richtige Größe der CPU, der Anzahl der Kerne und des Arbeitsspeichers für die Computer zu finden, die die Webdienste hosten.</span><span class="sxs-lookup"><span data-stu-id="3974e-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3974e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3974e-128">See Also</span></span>


[<span data-ttu-id="3974e-129">Überwachen der Speicher Kapazitätsgrenzwerte von Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3974e-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

