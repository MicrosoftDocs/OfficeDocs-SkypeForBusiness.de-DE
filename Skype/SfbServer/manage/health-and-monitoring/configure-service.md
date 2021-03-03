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
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817035"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Konfigurieren des Mobilitätsdiensts für hohe Leistung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst in Skype for Business Server.
  
> [!IMPORTANT]
> Dieses Thema gilt nur für den Skype for Business Server Mobility Service (Mcx) und nicht für unified Communications Web API (UCWA), wie in den kumulativen Updates für Lync Server 2013: Februar 2013 bereitgestellt. 
  
Wenn Sie den Mobilitätsdienst (Mcx) auf Internetinformationsdienste (IIS) 7.5 installieren, konfiguriert das Installationsprogramm für den Mobilitätsdienst einige Leistungseinstellungen auf dem Front-End-Server. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.
  
Hier sind die Leistungseinstellungen:
  
### <a name="settings-for-mcx-on-iis-75"></a>Einstellungen für Mcx unter IIS 7.5

1. **maxConcurrentThreadsPerCPU** ist auf null (0) gesetzt.
    
2. **maxConcurrentRequestsPerCPU** ist auf null (0) gesetzt.
    
3. Das ASP.NET-Prozessmodell ist auf "AutoConfig" (nur für IIS 7.5) gesetzt.
    
4. Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.
    

