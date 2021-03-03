---
title: Endgültige Prüfliste für die Bereitstellung der Anrufsteuerung für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Abschließende Prüfliste für die Bereitstellung der Anrufsteuerung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830835"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Bereitstellung der Anrufsteuerung: Endgültige Prüfliste für Skype for Business Server
 
Abschließende Prüfliste für die Bereitstellung der Anrufsteuerung in Skype for Business Server Enterprise-VoIP. 
  
Überprüfen Sie anhand der folgenden Prüfliste, ob Sie alle erforderlichen Konfigurationsaufgaben für die Bereitstellung der Anrufsteuerung abgeschlossen haben.
  
- Wenn ein oder mehrere Edgeserver bereitgestellt wurden, muss die IP-Adresse jeder externen Schnittstelle der Subnetzliste in den Netzwerkkonfigurationseinstellungen mit der Bitmaske 32 hinzugefügt werden. Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.
    
    > [!NOTE]
    > Edgeserver sind nicht erforderlich, um die Cac zu implementieren. 
  
- Stellen Sie sicher, dass die Anrufsteuerung aktiviert ist, wie unter ["Anrufsteuerung in Skype for Business Server aktivieren" angegeben.](enable-call-admission-control.md)
    
- Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist. Dies kann über den Topologie-Generator durchgeführt werden. Wenn beim Veröffentlichen eine Warnung generiert wird,  *ignorieren Sie sie*  nicht.
    
- Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Außerdem ist es wichtig, dass jedes Subnetz einem Netzwerkstandort zugeordnet ist, wie in "Bereitstellen von Netzwerkregionen, Standorten und Subnetzen [in Skype for Business" erläutert.](deploy-network.md)
    
- Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.
    

