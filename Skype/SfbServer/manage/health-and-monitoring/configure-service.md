---
title: Konfigurieren des Mobilitätsdienstes für hohe Leistung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst in Skype für Business Server 2015.'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a>Konfigurieren des Mobilitätsdienstes für hohe Leistung in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst in Skype für Business Server 2015.
  
> [!IMPORTANT]
> Dieses Thema bezieht sich nur auf die Skype für Business Server 2015 Mobility Service ("MCX") und bezieht sich nicht auf Unified Communications Web API (UCWA), wie in den kumulativen Updates für Lync Server 2013 übermittelt: für Februar 2013. 
  
Wenn Sie den Mobilitätsdienst ("MCX") auf Internetinformationsdienste (IIS) 7.5 installieren, wird das Installationsprogramm Mobility Service einige Leistungseinstellungen auf dem Front-End-Server konfiguriert. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.
  
Die Leistungseinstellungen lauten wie folgt:
  
### <a name="settings-for-mcx-on-iis-75"></a>Einstellungen für Mcx auf IIS 7.5

1. **MaxConcurrentThreadsPerCPU** ist auf Null (0) festgelegt.
    
2. **MaxConcurrentRequestsPerCPU** ist auf Null (0) festgelegt.
    
3. Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.
    
4. Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.
    

