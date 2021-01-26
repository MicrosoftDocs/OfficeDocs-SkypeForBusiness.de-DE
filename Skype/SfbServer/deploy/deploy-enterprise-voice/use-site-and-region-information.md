---
title: Konfigurieren globaler Einstellungen für die Medienumgehung in Skype for Business Server für die Verwendung von Standort- und Regioneninformationen
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Konfigurieren Sie die Medienumgehung so, dass sie nur für bestimmte Standorte und Regionen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830585"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Konfigurieren globaler Einstellungen für die Medienumgehung in Skype for Business Server für die Verwendung von Standort- und Regioneninformationen
 
Konfigurieren Sie die Medienumgehung so, dass sie nur für bestimmte Standorte und Regionen in Skype for Business Server Enterprise-VoIP. 
  
 Wenn Sie die globalen Einstellungen für die Medienumgehung mithilfe der Schritte in diesem Thema konfigurieren, wird davon ausgegangen, dass Sie nicht über eine gute Konnektivität zwischen allen Skype for Business-Endpunkten und einem Peer verfügen, für den Sie die Medienumgehung für die Trunkverbindung konfiguriert haben.
  
> [!NOTE]
> Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten. 
  
Damit die Medienumgehung ordnungsgemäß funktioniert, muss die Konsistenz zwischen einem Standort gemäß der Definition im Topologie-Generator und der Definition beim Konfigurieren von Netzwerkregionen und Netzwerkstandorten vorhanden sein. Wenn Sie beispielsweise über einen Zweigstellenstandort verfügen, den Sie im Topologie-Generator so definiert haben, dass nur ein PstN-Gateway bereitgestellt wird, muss dieser Zweigstellenstandort mit einer Enterprise-VoIP-Richtlinie konfiguriert werden, die es Zweigstellenbenutzern ermöglicht, ihre Festnetzanrufe über das Gateway im Telefonnetz am Zweigstellenstandort weiter zu routen.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung

1. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.
    
4. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.
    
5. Klicken Sie auf **Konfiguration von Standorten und Regionen verwenden**.
    
6. Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.
    
    > [!NOTE]
    > Aktivieren Sie dieses Kontrollkästchen nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigstandorten zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde. 
  
7. Klicken Sie auf **Commit**.
    
Fügen Sie als Nächstes Subnetze zum Netzwerkstandort hinzu, wie in "Zuordnen eines Subnetzes [zu einem Netzwerkstandort" beschrieben.](deploy-network.md#BKMK_AssociateSubnets) Nachdem Sie alle Subnetze zu Netzwerkstandorten zugeordnet haben, ist die Bereitstellung der Medienumgehung abgeschlossen.
> [!IMPORTANT]
> Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können. Weitere Informationen finden Sie [unter "Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business".](deploy-network.md) 
  
## <a name="see-also"></a>Siehe auch

[Zuordnen eines Subnetzes zu einem Netzwerkstandort](deploy-network.md#BKMK_AssociateSubnets)

