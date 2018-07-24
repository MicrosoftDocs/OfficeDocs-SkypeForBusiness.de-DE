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
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst in Skype für Business Server.
  
> [!IMPORTANT]
> Dieses Thema bezieht sich nur auf die Skype für Business Server Mobility Service ("MCX") und bezieht sich nicht auf Unified Communications Web API (UCWA), wie in den kumulativen Updates für Lync Server 2013 übermittelt: für Februar 2013. 
  
Wenn Sie den Mobilitätsdienst ("MCX") auf Internetinformationsdienste (IIS) 7.5 installieren, wird das Installationsprogramm Mobility Service einige Leistungseinstellungen auf dem Front-End-Server konfiguriert. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.
  
Die Leistungseinstellungen lauten wie folgt:
  
### <a name="settings-for-mcx-on-iis-75"></a>Einstellungen für Mcx auf IIS 7.5

1. **MaxConcurrentThreadsPerCPU** ist auf Null (0) festgelegt.
    
2. **MaxConcurrentRequestsPerCPU** ist auf Null (0) festgelegt.
    
3. Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.
    
4. Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.
    

