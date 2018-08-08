---
title: Konfigurieren von globalen Einstellungen für die medienumgehung in Skype für Business Server der Standorte und Regionen verwenden
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Konfigurieren der medienumgehung nur für bestimmte Standorte und Regionen in Skype für Business Server Enterprise-VoIP verwendet werden.
ms.openlocfilehash: 081be80d969c2503abc7e2de4e9865b6057a363b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995979"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Konfigurieren von globalen Einstellungen für die medienumgehung in Skype für Business Server der Standorte und Regionen verwenden
 
Konfigurieren der medienumgehung nur für bestimmte Standorte und Regionen in Skype für Business Server Enterprise-VoIP verwendet werden. 
  
 Wenn Sie die Schritte in diesem Thema zum Konfigurieren der globaler Einstellungen für Medien umgehen, wird davon ausgegangen, dass Sie keine gute Verbindung zwischen allen Skype für Business-Endpunkte und alle Peer für die medienumgehung für die trunkverbindung konfiguriert.
  
> [!NOTE]
> Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten. 
  
Vorhanden für die medienumgehung für die Verwendung ordnungsgemäß muss sein Konsistenz zwischen einer Website gemäß Definition im Topologie-Generator, und wie sie beim Konfigurieren von netzwerkregionen und Netzwerkstandorte definiert ist. Beispielsweise bei einer Zweigniederlassung, die Sie im Topologie-Generator definiert, dass haben nur ein PSTN-Gateway bereitgestellt, und klicken Sie dann, Zweigstellenstandort muss konfiguriert werden, mit einer Enterprise-VoIP-Richtlinie, mit die Benutzer des zweigstellenstandorts ihre PSTN-Anrufe über das PSTN weitergeleitet werden können Gateway am Zweigstellenstandort.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung

1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
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
> Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können. Weitere Informationen hierzu finden Sie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Unternehmen](deploy-network.md). 
  
## <a name="see-also"></a>Siehe auch

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

