---
title: Konfigurieren des mobilitätsdiensts für eine leistungsstarke Funktion in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Zusammenfassung: erfahren Sie mehr über den Mobilitätsdienst in Skype for Business Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305843"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Konfigurieren des mobilitätsdiensts für eine leistungsstarke Funktion in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Mobilitätsdienst in Skype for Business Server.
  
> [!IMPORTANT]
> Dieses Thema bezieht sich nur auf den Skype for Business Server-Mobilitätsdienst (MCX) und gilt nicht für Unified Communications Web API (UCWA), wie es in den kumulativen Updates für lync Server 2013: Februar 2013 bereitgestellt wird. 
  
Wenn Sie den Mobilitätsdienst (MCX) auf Internet Informationsdienste (IIS) 7,5 installieren, konfiguriert das Mobilitätsdienst-Installationsprogramm einige Leistungseinstellungen auf dem Front-End-Server. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.
  
Die Leistungseinstellungen lauten wie folgt:
  
### <a name="settings-for-mcx-on-iis-75"></a>Einstellungen für Mcx auf IIS 7.5

1. **maxConcurrentThreadsPerCPU** ist auf null (0) gesetzt.
    
2. **maxConcurrentRequestsPerCPU** ist auf null (0) gesetzt.
    
3. Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.
    
4. Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.
    

