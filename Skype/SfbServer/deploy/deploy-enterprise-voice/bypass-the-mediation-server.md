---
title: Konfigurieren der medienumgehung in Skype für Business Server 2015 zum dauerhaften Umgehung des Vermittlungsservers
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Aktivieren Sie die medienumgehung auf immer Umgehung des Vermittlungsservers in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: d7a80d9fb0365dde437f10696b13262f8667addf
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a>Konfigurieren der medienumgehung in Skype für Business Server 2015 zum dauerhaften Umgehung des Vermittlungsservers
 
Aktivieren Sie die medienumgehung auf immer Umgehung des Vermittlungsservers in Skype für Business Server Enterprise-VoIP. 
  
 Wenn Sie die Schritte in diesem Thema zum Konfigurieren der globaler Einstellungen für Medien umgehen, wird davon ausgegangen, dass Sie gute Verbindung zwischen Skype für Business-Endpunkte und alle Peer für die medienumgehung für die trunkverbindung konfiguriert haben.
  
Wenn Sie keine gute Verbindung zwischen Skype für Business-Endpunkte und alle Peers an den Vermittlungsserver, deren jeweiligen trunkverbindungen für die medienumgehung aktiviert wurden, müssen Sie Einstellungen für globale die medienumgehung Verwendung von Website und Regionsinformationen konfigurieren. Wenn Sie die medienumgehung verwenden. Dies ermöglicht mehr Kontrolle bei der Bestimmung, wenn Medien für den Vermittlungsserver umgeht. Zu diesem Zweck verwenden Sie stattdessen die Schritte unter [Configure Media bypass global Settings in Skype für Business Server 2015 Standorten und Regionen verwenden](use-site-and-region-information.md) and [ein Subnetz einem Netzwerkstandort zuzuordnen](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers

1. Öffnen von Skype Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Doppelklicken Sie in der Liste auf die Konfiguration **Global**.
    
4. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.
    
5. Klicken Sie auf **Immer umgehen**.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

#### 

[Planen Sie für die medienumgehung in Skype für Business 2015](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Bereitstellen von medienumgehung in Skype für Business Server 2015](deploy-media-bypass.md)

