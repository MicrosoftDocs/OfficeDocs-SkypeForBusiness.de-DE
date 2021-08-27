---
title: Konfigurieren der globalen Einstellungen für die Medienumgehung in Skype for Business Server für die Verwendung von Standort- und Regionsinformationen
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Konfigurieren Sie die Medienumgehung so, dass sie nur für bestimmte Standorte und Regionen in Skype for Business Server Enterprise-VoIP verwendet wird.
ms.openlocfilehash: d90393c19dffaac425025379258a0ceae24da9cf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588987"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Konfigurieren der globalen Einstellungen für die Medienumgehung in Skype for Business Server für die Verwendung von Standort- und Regionsinformationen
 
Konfigurieren Sie die Medienumgehung so, dass sie nur für bestimmte Standorte und Regionen in Skype for Business Server Enterprise-VoIP verwendet wird. 
  
 Wenn Sie die Schritte in diesem Thema verwenden, um globale Einstellungen für die Medienumgehung zu konfigurieren, wird davon ausgegangen, dass sie nicht über eine gute Verbindung zwischen allen Skype for Business Endpunkten und allen Peers verfügen, für die Sie die Medienumgehung für die Trunkverbindung konfiguriert haben.
  
> [!NOTE]
> Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten. 
  
Damit die Medienumgehung ordnungsgemäß funktioniert, muss eine Konsistenz zwischen einem Standort bestehen, der im Topologie-Generator definiert ist, und der Definition beim Konfigurieren von Netzwerkregionen und Netzwerkstandorten. Wenn Sie beispielsweise über einen Zweigstellenstandort verfügen, den Sie im Topologie-Generator so definiert haben, dass nur ein PSTN-Gateway bereitgestellt wird, muss dieser Zweigstellenstandort mit einer Enterprise-VoIP Richtlinie konfiguriert werden, die es Benutzern von Zweigstellenstandorten ermöglicht, ihre PSTN-Anrufe über das PSTN-Gateway am Zweigstellenstandort weiterzuleiten.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung

1. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.
    
4. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.
    
5. Klicken Sie auf **Konfiguration von Standorten und Regionen verwenden**.
    
6. Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.
    
    > [!NOTE]
    > Aktivieren Sie dieses Kontrollkästchen nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigstandorten zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde. 
  
7. Klicken Sie auf **Commit**.
    
Fügen Sie als Nächstes Subnetze zum Netzwerkstandort hinzu, wie unter ["Zuordnen eines Subnetzes zu einem Netzwerkstandort"](deploy-network.md#BKMK_AssociateSubnets)beschrieben. Nachdem Sie alle Subnetze zu Netzwerkstandorten zugeordnet haben, ist die Bereitstellung der Medienumgehung abgeschlossen.
> [!IMPORTANT]
> Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können. Ausführliche Informationen finden Sie unter [Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business.](deploy-network.md) 
  
## <a name="see-also"></a>Siehe auch

[Zuordnen eines Subnetzes zu einem Netzwerkstandort](deploy-network.md#BKMK_AssociateSubnets)

