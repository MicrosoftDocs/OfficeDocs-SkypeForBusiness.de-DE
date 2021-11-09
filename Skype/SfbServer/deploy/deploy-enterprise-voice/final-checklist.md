---
title: Endgültige Prüfliste für die Bereitstellung der Anrufsteuerung für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Letzte Prüfliste für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: ca9162604d1a25ecbde0df800e891931cd756d99
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855109"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Bereitstellung der Anrufsteuerung: abschließende Prüfliste für Skype for Business Server
 
Letzte Prüfliste für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in Skype for Business Server Enterprise-VoIP. 
  
Überprüfen Sie anhand der folgenden Prüfliste, ob Sie alle erforderlichen Konfigurationsaufgaben zum Bereitstellen der Anrufsteuerung (Call Admission Control, CAC) ausgeführt haben.
  
- Wenn ein oder mehrere Edgeserver bereitgestellt wurden, muss die IP-Adresse jeder externen Schnittstelle der Subnetzliste in den Netzwerkkonfigurationseinstellungen mit der Bitmaske 32 hinzugefügt werden. Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.
    
    > [!NOTE]
    > Edgeserver sind nicht erforderlich, um die Anrufsteuerung zu implementieren. 
  
- Stellen Sie sicher, dass die Anrufsteuerung aktiviert ist, wie unter Aktivieren der [Anrufsteuerung in Skype for Business Server](enable-call-admission-control.md)angegeben.
    
- Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist. Dies kann über den Topologie-Generator erfolgen. Wenn beim Veröffentlichen eine Warnung generiert wird, ignorieren Sie sie *nicht.*
    
- Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Es ist auch wichtig, dass jedes Subnetz einem Netzwerkstandort zugeordnet wird, wie unter [Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business](deploy-network.md)erläutert.
    
- Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.
    

