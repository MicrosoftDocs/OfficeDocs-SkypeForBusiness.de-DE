---
title: Konfigurieren des Mobilitätsdiensts für hohe Leistung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Zusammenfassung: Erfahren Sie mehr über den Mobilitätsdienst in Skype for Business Server.'
ms.openlocfilehash: 3029877aa6f252ada9bbb38bca0148b8a96908ad5cf4deded7cf48e6451ec833
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298135"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Konfigurieren des Mobilitätsdiensts für hohe Leistung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst in Skype for Business Server.
  
> [!IMPORTANT]
> Dieses Thema gilt nur für den Skype for Business Server Mobility Service (Mcx) und nicht für Unified Communications Web API (UCWA), wie in den kumulativen Updates für Lync Server 2013 bereitgestellt: Februar 2013. 
  
Wenn Sie den Mobilitätsdienst (Mcx) auf Internetinformationsdienste (IIS) 7.5 installieren, konfiguriert das Installationsprogramm für den Mobilitätsdienst einige Leistungseinstellungen auf dem Front-End-Server. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.
  
Hier sind die Leistungseinstellungen:
  
### <a name="settings-for-mcx-on-iis-75"></a>Einstellungen für Mcx unter IIS 7.5

1. **maxConcurrentThreadsPerCPU** ist auf null (0) gesetzt.
    
2. **maxConcurrentRequestsPerCPU** ist auf null (0) gesetzt.
    
3. Das ASP.NET-Prozessmodell ist auf "AutoConfig" (nur für IIS 7.5) gesetzt.
    
4. Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.
    

