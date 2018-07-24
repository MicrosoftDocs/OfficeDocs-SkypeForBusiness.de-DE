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
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990637"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="d73b3-103">Überwachen der Mobilität für die Leistung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d73b3-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="d73b3-104">**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="d73b3-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="d73b3-105">Die Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) erhöhen die Last auf dem Front-End-Servern und Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="d73b3-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="d73b3-106">Mobile Geräte, die eine Verbindung mit dem Server verwalten, auch wenn die mobile Anwendung minimiert wird, wie beispielsweise Android- und Nokia-Geräte, die mit Lync 2010 Mobile sowie Android und Apple-Geräte, die mit Lync 2013 Mobile bedingen eine größere Belastung als Geräte, Ihre Verbindung mit dem Server zu beenden, wenn die mobile Anwendung minimiert ist.</span><span class="sxs-lookup"><span data-stu-id="d73b3-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="d73b3-107">Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.</span><span class="sxs-lookup"><span data-stu-id="d73b3-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="d73b3-108">MCX-Unterstützung für mobile Clients von Vorversionen ist nicht mehr in Skype für Business Server 2019 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d73b3-108">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d73b3-109">Die Benutzer müssen an einen aktuellen Client aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d73b3-109">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="d73b3-110">Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:</span><span class="sxs-lookup"><span data-stu-id="d73b3-110">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="d73b3-111">Verfügbarer Speicher</span><span class="sxs-lookup"><span data-stu-id="d73b3-111">Available memory</span></span>
    
- <span data-ttu-id="d73b3-112">Anforderungswarteschlangenlimit</span><span class="sxs-lookup"><span data-stu-id="d73b3-112">Request queue limit</span></span>
    
- <span data-ttu-id="d73b3-113">Gleichzeitige Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d73b3-113">Concurrent connections</span></span>
    
- <span data-ttu-id="d73b3-114">IIS-Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="d73b3-114">IIS queue length</span></span>
    
<span data-ttu-id="d73b3-p103">Darüber hinaus wirken sich andere Serverlimits auf die Mobilitätsleistung aus. Hierzu gehören maximal 12 gleichzeitige Anmeldungen, Authentifizierungen und Sitzungserneuerungen und -beendigungen. Für die meisten Bereitstellungen müssen die Maximalwerte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d73b3-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d73b3-117">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="d73b3-117">In this section</span></span>

- [<span data-ttu-id="d73b3-118">Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d73b3-118">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="d73b3-119">Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d73b3-119">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="d73b3-120">Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d73b3-120">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="d73b3-121">Monitoring IIS Request tracing Log Files in der Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d73b3-121">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="d73b3-122">Leistungsindikatoren für Mobilität in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d73b3-122">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

