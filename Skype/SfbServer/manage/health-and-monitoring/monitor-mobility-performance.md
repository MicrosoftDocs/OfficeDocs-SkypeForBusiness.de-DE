---
title: Überwachen der Mobilität in Bezug auf die Leistung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications in Skype für Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="b3a61-103">Überwachen der Mobilität in Bezug auf die Leistung in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3a61-103">Monitor mobility for performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b3a61-104">**Zusammenfassung:** Informieren Sie sich über den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b3a61-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b3a61-105">Die Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) erhöhen die Last auf dem Front-End-Servern und Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="b3a61-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="b3a61-106">Mobile Geräte, die eine Verbindung mit dem Server verwalten, auch wenn die mobile Anwendung minimiert wird, wie beispielsweise Android- und Nokia-Geräte, die mit Lync 2010 Mobile sowie Android und Apple-Geräte, die mit Lync 2013 Mobile bedingen eine größere Belastung als Geräte, Ihre Verbindung mit dem Server zu beenden, wenn die mobile Anwendung minimiert ist.</span><span class="sxs-lookup"><span data-stu-id="b3a61-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="b3a61-107">Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.</span><span class="sxs-lookup"><span data-stu-id="b3a61-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>
  
<span data-ttu-id="b3a61-108">Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:</span><span class="sxs-lookup"><span data-stu-id="b3a61-108">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="b3a61-109">Verfügbarer Speicher</span><span class="sxs-lookup"><span data-stu-id="b3a61-109">Available memory</span></span>
    
- <span data-ttu-id="b3a61-110">Anforderungswarteschlangenlimit</span><span class="sxs-lookup"><span data-stu-id="b3a61-110">Request queue limit</span></span>
    
- <span data-ttu-id="b3a61-111">Gleichzeitige Verbindungen</span><span class="sxs-lookup"><span data-stu-id="b3a61-111">Concurrent connections</span></span>
    
- <span data-ttu-id="b3a61-112">IIS-Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="b3a61-112">IIS queue length</span></span>
    
<span data-ttu-id="b3a61-p102">Darüber hinaus wirken sich andere Serverlimits auf die Mobilitätsleistung aus. Hierzu gehören maximal 12 gleichzeitige Anmeldungen, Authentifizierungen und Sitzungserneuerungen und -beendigungen. Für die meisten Bereitstellungen müssen die Maximalwerte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b3a61-p102">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b3a61-115">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="b3a61-115">In this section</span></span>

- [<span data-ttu-id="b3a61-116">Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3a61-116">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="b3a61-117">Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3a61-117">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="b3a61-118">Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3a61-118">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>](configure-service.md)
    
- [<span data-ttu-id="b3a61-119">Monitoring IIS request Tracing Log Files in der Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3a61-119">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="b3a61-120">Leistungsindikatoren für Mobilität in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3a61-120">Mobility performance counters in Skype for Business Server 2015</span></span>](performance-counters.md)
    

