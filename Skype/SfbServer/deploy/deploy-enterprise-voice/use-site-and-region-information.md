---
title: Konfigurieren der globalen Einstellungen für medienumgehung in Skype for Business Server für die Verwendung von Website-und Regionsinformationen
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Konfigurieren Sie die medienumgehung so, dass Sie nur für bestimmte Websites und Regionen in Skype for Business Server Enterprise Voice verwendet werden kann.
ms.openlocfilehash: 7a424e6737c1165eb037ca1130e3b87c4d0436e0
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766938"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Konfigurieren der globalen Einstellungen für medienumgehung in Skype for Business Server für die Verwendung von Website-und Regionsinformationen
 
Konfigurieren Sie die medienumgehung so, dass Sie nur für bestimmte Websites und Regionen in Skype for Business Server Enterprise Voice verwendet werden kann. 
  
 Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, wird davon ausgegangen, dass Sie keine gute Verbindung zwischen allen Skype for Business-Endpunkten und allen Peers haben, für die Sie die medienumgehung für die trunk-Verbindung konfiguriert haben.
  
> [!NOTE]
> Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten. 
  
Damit die medienumgehung ordnungsgemäß funktioniert, muss die Konsistenz zwischen einer Website, wie Sie in Topology Builder definiert ist, und der Definition beim Konfigurieren von netzwerkregionen und Netzwerk Websites bestehen. Wenn Sie beispielsweise über eine Verzweigungs Website verfügen, die Sie im Topologie-Generator definiert haben, als ob nur ein PSTN-Gateway bereitgestellt wurde, muss diese Verzweigungs Website mit einer Enterprise-VoIP-Richtlinie konfiguriert werden, die es den Benutzern der Zweigstelle ermöglicht, ihre PSTN-Anrufe über das PSTN weiterzuleiten. Gateway an der Verzweigungs Website.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung

1. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.
    
4. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.
    
5. Klicken Sie auf **Standort- und Regionskonfiguration verwenden**.
    
6. Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.
    
    > [!NOTE]
    > Aktivieren Sie dieses Kontrollkästchen nur, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigniederlassungen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigniederlassungen zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde. 
  
7. Klicken Sie auf **Commit ausführen**.
    
Fügen Sie anschließend Subnetze zum Netzwerkstandort hinzu, wie unter [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) beschrieben. Nachdem Sie alle Subnetze zu Netzwerkstandorten zugeordnet haben, ist die Bereitstellung der Medienumgehung abgeschlossen.
> [!IMPORTANT]
> Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können. Ausführliche Informationen finden Sie unter [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business](deploy-network.md). 
  
## <a name="see-also"></a>Siehe auch

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

