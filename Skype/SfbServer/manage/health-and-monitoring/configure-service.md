---
title: Konfigurieren des mobilitätsdiensts für eine leistungsstarke Funktion in Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Zusammenfassung: erfahren Sie mehr über den Mobilitätsdienst in Skype for Business Server.'
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818055"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="31400-103">Konfigurieren des mobilitätsdiensts für eine leistungsstarke Funktion in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="31400-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="31400-104">**Zusammenfassung:** Informieren Sie sich über den Mobilitätsdienst in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="31400-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="31400-105">Dieses Thema bezieht sich nur auf den Skype for Business Server-Mobilitätsdienst (MCX) und gilt nicht für Unified Communications Web API (UCWA), wie es in den kumulativen Updates für lync Server 2013: Februar 2013 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="31400-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="31400-106">Wenn Sie den Mobilitätsdienst (MCX) auf Internet Informationsdienste (IIS) 7,5 installieren, konfiguriert das Mobilitätsdienst-Installationsprogramm einige Leistungseinstellungen auf dem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="31400-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="31400-107">Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="31400-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="31400-108">Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="31400-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="31400-109">Die Leistungseinstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="31400-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="31400-110">Einstellungen für Mcx auf IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="31400-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="31400-111">**maxConcurrentThreadsPerCPU** ist auf null (0) gesetzt.</span><span class="sxs-lookup"><span data-stu-id="31400-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="31400-112">**maxConcurrentRequestsPerCPU** ist auf null (0) gesetzt.</span><span class="sxs-lookup"><span data-stu-id="31400-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="31400-113">Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.</span><span class="sxs-lookup"><span data-stu-id="31400-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="31400-114">Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.</span><span class="sxs-lookup"><span data-stu-id="31400-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

