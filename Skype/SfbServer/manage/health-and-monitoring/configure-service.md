---
title: Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst in Skype für Business Server.'
ms.openlocfilehash: 5031d34a2fdcb1610325afbf58c5524a0ee28ca8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026806"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="75075-103">Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="75075-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="75075-104">**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="75075-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="75075-105">Dieses Thema bezieht sich nur auf die Skype für Business Server Mobility Service ("MCX") und bezieht sich nicht auf Unified Communications Web API (UCWA), wie in den kumulativen Updates für Lync Server 2013 übermittelt: für Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="75075-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="75075-106">Wenn Sie den Mobilitätsdienst ("MCX") auf Internetinformationsdienste (IIS) 7.5 installieren, wird das Installationsprogramm Mobility Service einige Leistungseinstellungen auf dem Front-End-Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="75075-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="75075-107">Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="75075-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="75075-108">Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="75075-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="75075-109">Die Leistungseinstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="75075-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="75075-110">Einstellungen für Mcx auf IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="75075-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="75075-111">**MaxConcurrentThreadsPerCPU** ist auf Null (0) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75075-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="75075-112">**MaxConcurrentRequestsPerCPU** ist auf Null (0) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75075-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="75075-113">Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.</span><span class="sxs-lookup"><span data-stu-id="75075-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="75075-114">Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.</span><span class="sxs-lookup"><span data-stu-id="75075-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

