---
title: Konfigurieren von Trunks in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren eines Trunks zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype für Business Server 2015.'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>Konfigurieren von Trunks in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Trunk zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype für Business Server 2015 konfigurieren.
  
Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und mindestens eine der folgenden Peers zum öffentlichen Telefonnetz (PSTN) Netzwerkkonnektivität für Enterprise-VoIP-Clients und Geräte in Ihrer Organisation bereitstellen konfigurieren:
  
- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
    
- PSTN-Gateway
    
- Nebenstellenanlage (Private Branch Exchange, PBX)
    
Weitere Informationen finden Sie unter [Planen der PSTN-Konnektivität in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype-Funktionen, Business Server unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden geändert, indem ein Trunk eine logische Zuordnung zwischen einem vermittlungsserverpool und einem Gateway public switched Telephone Network (Telefonfestnetz PSTN), Session Border Controller (SBC) oder IP-PBX ist zu definieren. Verwenden Sie den Topologie-Generator Vermittlungsserver (d. h., Trunks) Gateways zugeordnet.
  
- Zum Zuweisen oder Entfernen eines Trunks in Skype für Business Server, müssen Sie zuerst einen Trunk im Topologie-Generator definieren. Ein Trunk umfasst die folgenden Zuordnung: Vermittlungsserver vollqualifizierter Domänenname (FQDN), den Vermittlungsserver Überwachungsport, FQDN des Gateways und den Überwachungsport des Gateways.
    
- Um mehrere Trunks zu konfigurieren, können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungsserver erstellen. Dadurch wird die zusätzliche Flexibilität mit der Enterprise-VoIP-Infrastruktur in private Branch Exchange, (Nebenstellenanlage PBX) interoperational Szenarien besonders nützlich ist. 
    
Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Um einen Trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für die Trunks im Topologie-Generator. Diese einfache Name wird als den trunknamen in der Skype Business Server-Systemsteuerung verwendet, in dem Trunks Routen zugeordnet werden kann. Der einfachen trunknamen dient als Gateway-Namen aus der Skype für Business Server-Verwaltungsshell. 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

Der Administrator muss einen Standard-Trunk zugeordnet eines Vermittlungsservers auswählen. Topologie-Generator mit der rechten Maustaste zugeordneter Vermittlungsserver, und klicken Sie dann auf **Eigenschaften**. Geben Sie den Standard-Gateway für den Vermittlungsserver. 
  

