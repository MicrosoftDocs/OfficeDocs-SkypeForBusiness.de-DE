---
title: Konfigurieren der medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Aktivieren Sie die medienumgehung, um den Vermittlungsserver in Skype for Business Server Enterprise Voice immer zu umgehen.
ms.openlocfilehash: cde2a1bff41016e05ac6c74978fa65b45f11a1e7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768268"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Konfigurieren der medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen
 
Aktivieren Sie die medienumgehung, um den Vermittlungsserver in Skype for Business Server Enterprise Voice immer zu umgehen. 
  
 Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, besteht die Annahme, dass Sie über eine gute Verbindung zwischen den Endpunkten von Skype for Business und allen Peers verfügen, für die Sie die medienumgehung für die trunk-Verbindung konfiguriert haben.
  
Wenn Sie keine gute Verbindung zwischen Skype for Business-Endpunkten und allen Peers mit dem Vermittlungs Server haben, deren jeweilige trunk-Verbindungen für die medienumgehung aktiviert wurden, müssen Sie die globalen Einstellungen für die medienumgehung so konfigurieren, dass die Website-und Regionsinformationen verwendet werden. bei Verwendung der medienumgehung. Auf diese Weise können Sie festlegen, wann Medien den Vermittlungs Server umgeht. Führen Sie dazu die Schritte unter Konfigurieren der [globalen Einstellungen für medienumgehung in Skype for Business Server aus, um Website-und Regionsinformationen zu verwenden](use-site-and-region-information.md) und stattdessen [ein Subnetz mit einer Netzwerk Website zu verknüpfen](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Doppelklicken Sie in der Liste auf die Konfiguration **Global**.
    
4. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.
    
5. Klicken Sie auf **Immer umgehen**.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

[Planen der medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Bereitstellen der medienumgehung in Skype for Business Server](deploy-media-bypass.md)

