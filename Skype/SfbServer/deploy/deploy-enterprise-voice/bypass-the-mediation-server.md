---
title: Konfigurieren der Medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Aktivieren Sie die Medienumgehung, um den Vermittlungsserver in Skype for Business Server Enterprise-VoIP immer zu umgehen.
ms.openlocfilehash: ada5ce953086fe2182314bbe4904964683cb868c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764903"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Konfigurieren der Medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen
 
Aktivieren Sie die Medienumgehung, um den Vermittlungsserver in Skype for Business Server Enterprise-VoIP immer zu umgehen. 
  
 Wenn Sie die Schritte in diesem Thema verwenden, um globale Einstellungen für die Medienumgehung zu konfigurieren, wird davon ausgegangen, dass Sie über eine gute Verbindung zwischen Skype for Business Endpunkten und allen Peers verfügen, für die Sie die Medienumgehung für die Trunkverbindung konfiguriert haben.
  
Wenn sie keine gute Verbindung zwischen Skype for Business Endpunkten und allen Peers zum Vermittlungsserver haben, deren jeweilige Trunkverbindungen für die Medienumgehung aktiviert wurden, müssen Sie die Einstellungen für die globale Medienumgehung so konfigurieren, dass standort- und regionsübergreifende Informationen bei der Medienumgehung verwendet werden. Auf diese Weise kann die Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver besser gesteuert werden. Führen Sie dazu die Schritte unter Konfigurieren der globalen Einstellungen für die [Medienumgehung in Skype for Business Server aus, um Standort- und Regionsinformationen zu verwenden](use-site-and-region-information.md) und stattdessen [ein Subnetz einem Netzwerkstandort zuzuordnen.](deploy-network.md#BKMK_AssociateSubnets)
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers

1. Öffnen Sie Skype for Business Server Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Doppelklicken Sie in der Liste auf die Konfiguration **Global**.
    
4. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.
    
5. Klicken Sie auf **Immer umgehen**.
    
6. Klicken Sie auf **Commit**.
    
## <a name="see-also"></a>Weitere Informationen

[Planen der Medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Bereitstellen der Medienumgehung in Skype for Business Server](deploy-media-bypass.md)

