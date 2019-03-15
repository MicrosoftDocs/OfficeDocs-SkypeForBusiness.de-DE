---
title: Überwachen der Mobilität für die Leistung in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.'
ms.openlocfilehash: f4932a9ff14500aa16d2e183a3b665e7106302ee
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "21226917"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="e978b-103">Überwachen der Mobilität für die Leistung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e978b-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="e978b-104">**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="e978b-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="e978b-105">Die Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) erhöhen die Last auf dem Front-End-Servern und Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="e978b-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="e978b-106">Mobile Geräte, die eine Verbindung mit dem Server verwalten, auch wenn die mobile Anwendung minimiert wird, wie beispielsweise Android- und Nokia-Geräte, die mit Lync 2010 Mobile sowie Android und Apple-Geräte, die mit Lync 2013 Mobile bedingen eine größere Belastung als Geräte, Ihre Verbindung mit dem Server zu beenden, wenn die mobile Anwendung minimiert ist.</span><span class="sxs-lookup"><span data-stu-id="e978b-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="e978b-107">Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.</span><span class="sxs-lookup"><span data-stu-id="e978b-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="e978b-108">Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e978b-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e978b-109">Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden.</span><span class="sxs-lookup"><span data-stu-id="e978b-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e978b-110">Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e978b-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="e978b-111">Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:</span><span class="sxs-lookup"><span data-stu-id="e978b-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="e978b-112">Verfügbarer Speicher</span><span class="sxs-lookup"><span data-stu-id="e978b-112">Available memory</span></span>
    
- <span data-ttu-id="e978b-113">Anforderungswarteschlangenlimit</span><span class="sxs-lookup"><span data-stu-id="e978b-113">Request queue limit</span></span>
    
- <span data-ttu-id="e978b-114">Gleichzeitige Verbindungen</span><span class="sxs-lookup"><span data-stu-id="e978b-114">Concurrent connections</span></span>
    
- <span data-ttu-id="e978b-115">IIS-Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="e978b-115">IIS queue length</span></span>
    
<span data-ttu-id="e978b-p103">Darüber hinaus wirken sich andere Serverlimits auf die Mobilitätsleistung aus. Hierzu gehören maximal 12 gleichzeitige Anmeldungen, Authentifizierungen und Sitzungserneuerungen und -beendigungen. Für die meisten Bereitstellungen müssen die Maximalwerte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e978b-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e978b-118">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="e978b-118">In this section</span></span>

- [<span data-ttu-id="e978b-119">Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e978b-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="e978b-120">Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e978b-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="e978b-121">Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e978b-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="e978b-122">Monitoring IIS Request tracing Log Files in der Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e978b-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="e978b-123">Leistungsindikatoren für Mobilität in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e978b-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

