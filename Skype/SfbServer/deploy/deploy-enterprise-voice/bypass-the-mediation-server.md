---
title: Konfigurieren der Medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Aktivieren Sie die Medienumgehung, um den Vermittlungsserver in Skype for Business Server immer Enterprise-VoIP.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804215"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Konfigurieren der Medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen
 
Aktivieren Sie die Medienumgehung, um den Vermittlungsserver in Skype for Business Server immer Enterprise-VoIP. 
  
 Wenn Sie die globalen Einstellungen für die Medienumgehung mithilfe der Schritte in diesem Thema konfigurieren, wird davon ausgegangen, dass Sie über eine gute Konnektivität zwischen Skype for Business-Endpunkten und jedem Peer verfügen, für den Sie die Medienumgehung für die Trunkverbindung konfiguriert haben.
  
Wenn Sie keine gute Konnektivität zwischen Skype for Business-Endpunkten und allen Peers zum Vermittlungsserver haben, dessen entsprechende Trunkverbindungen für die Medienumgehung aktiviert wurden, müssen Sie globale Einstellungen für die Medienumgehung so konfigurieren, dass Standort- und Regioneninformationen verwendet werden, wenn Sie die Medienumgehung verwenden. Auf diese Weise kann die Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver besser gesteuert werden. Führen Sie dazu die Schritte unter "Konfigurieren der globalen Einstellungen für die Medienumgehung [in Skype for Business Server"](use-site-and-region-information.md) aus, um Standort- und Regioneninformationen zu verwenden, und ordnen Sie stattdessen ein Subnetz einem [Netzwerkstandort zu.](deploy-network.md#BKMK_AssociateSubnets)
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Doppelklicken Sie in der Liste auf die Konfiguration **Global**.
    
4. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.
    
5. Klicken Sie auf **Immer umgehen**.
    
6. Klicken Sie auf **Commit**.
    
## <a name="see-also"></a>Siehe auch

[Planen der Medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Bereitstellen der Medienumgehung in Skype for Business Server](deploy-media-bypass.md)

