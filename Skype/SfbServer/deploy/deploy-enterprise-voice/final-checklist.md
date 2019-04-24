---
title: Anruf Admission Control endgültigen Prüfliste zur Bereitstellung von Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Endgültige Checkliste für die Bereitstellung von Call Admission Control (CAC) in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: d0d61bcf6c6f0ab509eafa2b968bbb45c00b2a50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212404"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Rufen Sie die Bereitstellung der anrufsteuerung: endgültige Checkliste für Skype für Business Server
 
Endgültige Checkliste für die Bereitstellung von Call Admission Control (CAC) in Skype für Business Server Enterprise-VoIP. 
  
Überprüfen Sie anhand der folgenden Liste, ob Sie alle erforderlichen Konfigurationsaufgaben für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) abgeschlossen haben.
  
- Wenn eine oder mehrere Edgeserver bereitgestellt werden, muss jede externe IP-Adresse der Subnetliste in den netzwerkkonfigurationseinstellungen, denen eine Bitmaske 32 hinzugefügt werden. Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.
    
    > [!NOTE]
    > Edge-Server sind zum Implementieren der Anrufsteuerung nicht erforderlich. 
  
- Stellen Sie sicher, dass die Anrufsteuerung aktiviert ist, als der angegebene in [Aktivieren der anrufsteuerung in Skype für Business Server](enable-call-admission-control.md).
    
- Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist. Dies kann über den Topologie-Generator erfolgen. Wenn eine Warnung generiert wird, wenn Sie veröffentlichen, ignoriert *jedoch nicht* .
    
- Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Es ist außerdem wichtig, dass jedes Subnetz einem Netzwerkstandort zugeordnet werden soll, wie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Unternehmen](deploy-network.md)erläutert wird.
    
- Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.
    

